#### [Examine STIG V-257986](https://professionallinuxusersgroup.github.io/psc/u3lab.html#examine-stig-v-257986)

What is the problem?  
	RHEL 9 must enable the Pluggable Authentication Module (PAM) interface for SSHD
What is the fix?  
	Configure the RHEL 9 SSHD to use the UsePAM interface by adding or modifying the following line in "/etc/ssh/sshd_config" or in a file in "/etc/ssh/sshd_config.d".
What type of control is being implemented?  
Is it set properly on your system?

```bash
/usr/sbin/sshd -dd 2>&1 | awk '/filename/ {print $4}' | tr -d '\r' | tr '\n' ' ' | xargs grep -iH '^\s*usepam'
```
```bash
/etc/ssh/sshd_config.d/50-redhat.conf:UsePAM yes
```

```bash
grep -i pam /etc/ssh/sshd_config
```
```bash
# Set this to 'yes' to enable PAM authentication, account processing,
# and session processing. If this is enabled, PAM authentication will
# PasswordAuthentication.  Depending on your PAM configuration,
# PAM authentication via KbdInteractiveAuthentication may bypass
# If you just want the PAM account and session checks to run without
# PAM authentication, then enable this but set PasswordAuthentication
# WARNING: 'UsePAM no' is not supported in RHEL and may cause several
#UsePAM no
```
```bash
sed -i s/"#UsePAM no/UsePAM yes/" /etc/ssh/sshd_config
```

#### [Check and remediate STIG V-258055](https://professionallinuxusersgroup.github.io/psc/u3lab.html#check-and-remediate-stig-v-258055)

What is the problem?  
	RHEL 9 must automatically lock the root account until the root account is released by an administrator when three unsuccessful logon attempts occur during a 15-minute time period.
What is the fix?  
	To configure RHEL 9 to lock out the "root" account after a number of incorrect logon attempts using "pam_faillock.so", first enable the feature using the following command:
 
	$ sudo authselect enable-feature with-faillock  

	Edit the "/etc/security/faillock.conf" by uncommenting or adding the following line:
 
	even_deny_root
What type of control is being implemented?  
Are there any major implications to think about with this change on your system? Why or why not?  
Is it set properly on your system?  
```bash
# even_deny_root
# This option implies the `even_deny_root` option.
# the root account (the options `even_deny_root>` and
```
How would you go about remediating this on your system?
vi /etc/security/faillock.conf
#### [Check and remediate STIG V-258098](https://professionallinuxusersgroup.github.io/psc/u3lab.html#check-and-remediate-stig-v-258098)

What is the problem?  
	RHEL 9 must ensure the password complexity module is enabled in the system-auth file.
What is the fix?  
	Configure RHEL 9 to use "pwquality" to enforce password complexity rules.
What type of control is being implemented?  
Is it set properly on your system?
```bash
grep pam_pwquality /etc/pam.d/system-auth
```
```bash
password    requisite     pam_pwquality.so try_first_pass local_users_only retry=3 authtok_type=
```

How many are there?  14
What are the password complexity rules?
	maximum number of repeating characters be limited to three
	at least four character classes
	maximum number of repeating characters of the same character class be limited to four
	at least eight characters
	at least one uppercase character
	prevent the use of dictionary words
	at least one special character
	minimum of 15 characters.
	at least one numeric character
	at least one lowercase character
Are there any you haven't seen before?

#### [Filter by sssd](https://professionallinuxusersgroup.github.io/psc/u3lab.html#filter-by-sssd)

How many STIGS do you see?  6 (2 for smart card)
What do these STIGS appear to be trying to do? What types of controls are they?
	Setup public key authentication and cached duration

### [OpenLDAP Setup](https://professionallinuxusersgroup.github.io/psc/u3lab.html#openldap-setup)

```bash
systemctl stop wwclient
```
```bash
vi /etc/hosts
```
```bash
dnf config-manager --set-enabled plus
```
```bash
dnf repolist
```
```
repo id                                                                        repo name
appstream                                                                      Rocky Linux 9 - AppStream
baseos                                                                         Rocky Linux 9 - BaseOS
epel                                                                           Extra Packages for Enterprise Linux 9 - x86_64
epel-cisco-openh264                                                            Extra Packages for Enterprise Linux 9 openh264 (From Cisco) - x86_64
extras                                                                         Rocky Linux 9 - Extras
plus                                                                           Rocky Linux 9 - Plus
```
```bash
dnf -y install openldap-servers openldap-clients openldap
```

```bash
Rocky Linux 9 - Extras                                                                                                                                                        6.0 kB/s | 2.9 kB     00:00
Rocky Linux 9 - Plus                                                                                                                                                          5.6 kB/s | 4.6 kB     00:00
Package openldap-2.6.6-3.el9.x86_64 is already installed.
Dependencies resolved.
==============================================================================================================================================================================================================
 Package                                                Architecture                                 Version                                               Repository                                    Size
==============================================================================================================================================================================================================
Installing:
 openldap-clients                                       x86_64                                       2.6.8-4.el9.0.1                                       baseos                                       174 k
 openldap-servers                                       x86_64                                       2.6.8-4.el9.0.1                                       plus                                         2.3 M
Upgrading:
 openldap                                               x86_64                                       2.6.8-4.el9.0.1                                       baseos                                       256 k

Transaction Summary
==============================================================================================================================================================================================================
Install  2 Packages
Upgrade  1 Package

Total download size: 2.7 M
Downloading Packages:
Rocky Linux 9 - Plus                                                               203% [=====================================================================================================================(1/3): openldap-clients-2.6.8-4.el9.0.1.x86_64.rpm                                                                                                                            451 kB/s | 174 kB     00:00
(2/3): openldap-2.6.8-4.el9.0.1.x86_64.rpm                                                                                                                                    563 kB/s | 256 kB     00:00
(3/3): openldap-servers-2.6.8-4.el9.0.1.x86_64.rpm                                                                                                                            2.3 MB/s | 2.3 MB     00:01
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                         2.0 MB/s | 2.7 MB     00:01
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                      1/1
  Upgrading        : openldap-2.6.8-4.el9.0.1.x86_64                                                                                                                                                      1/4
  Installing       : openldap-clients-2.6.8-4.el9.0.1.x86_64                                                                                                                                              2/4
  Running scriptlet: openldap-servers-2.6.8-4.el9.0.1.x86_64                                                                                                                                              3/4
  Installing       : openldap-servers-2.6.8-4.el9.0.1.x86_64                                                                                                                                              3/4
  Running scriptlet: openldap-servers-2.6.8-4.el9.0.1.x86_64                                                                                                                                              3/4
  Cleanup          : openldap-2.6.6-3.el9.x86_64                                                                                                                                                          4/4
  Running scriptlet: openldap-2.6.6-3.el9.x86_64                                                                                                                                                          4/4
  Verifying        : openldap-clients-2.6.8-4.el9.0.1.x86_64                                                                                                                                              1/4
  Verifying        : openldap-servers-2.6.8-4.el9.0.1.x86_64                                                                                                                                              2/4
  Verifying        : openldap-2.6.8-4.el9.0.1.x86_64                                                                                                                                                      3/4
  Verifying        : openldap-2.6.6-3.el9.x86_64                                                                                                                                                          4/4

Upgraded:
  openldap-2.6.8-4.el9.0.1.x86_64
Installed:
  openldap-clients-2.6.8-4.el9.0.1.x86_64                                                               openldap-servers-2.6.8-4.el9.0.1.x86_64

Complete!
```
```bash
systemctl start slapd
```
```bash
ss -ntulp | grep slapd
```
```bash
tcp   LISTEN 0      2048         0.0.0.0:389       0.0.0.0:*    users:(("slapd",pid=21061,fd=7))
tcp   LISTEN 0      2048         0.0.0.0:636       0.0.0.0:*    users:(("slapd",pid=21061,fd=9))
tcp   LISTEN 0      2048            [::]:389          [::]:*    users:(("slapd",pid=21061,fd=8))
tcp   LISTEN 0      2048            [::]:636          [::]:*    users:(("slapd",pid=21061,fd=10))
```

```bash
firewall-cmd --add-service={ldap,ldaps} --permanent
```
```bash
firewall-cmd --add-service={ldap,ldaps}
```
```bash
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: eth0
  sources:
  services: cockpit dhcpv6-client ldap ldaps prometheus-node-exporter ssh
  ports:
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
```
```bash
slappasswd
```
```bash
{SSHA}cpPkiE9u25pPvegs2ndMBRd9FUfmU3DW
```
```bash
ldapadd -Y EXTERNAL -H ldapi:/// -f changerootpass.ldif
```
```bash
SASL/EXTERNAL authentication started
SASL username: gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth
SASL SSF: 0
modifying entry "olcDatabase={0}config,cn=config"
```
```bash
ldapadd -Y EXTERNAL -H ldapi:/// -f /etc/openldap/schema/cosine.ldif
```
```bash
SASL/EXTERNAL authentication started
SASL username: gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth
SASL SSF: 0
adding new entry "cn=cosine,cn=schema,cn=config"
```
```bash
ldapadd -Y EXTERNAL -H ldapi:/// -f /etc/openldap/schema/nis.ldif
```
```bash
SASL/EXTERNAL authentication started
SASL username: gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth
SASL SSF: 0
adding new entry "cn=nis,cn=schema,cn=config"
```
```bash
ldapadd -Y EXTERNAL -H ldapi:/// -f /etc/openldap/schema/inetorgperson.ldif
```
```bash
SASL/EXTERNAL authentication started
SASL username: gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth
SASL SSF: 0
adding new entry "cn=inetorgperson,cn=schema,cn=config"
```
```bash
ldapmodify -Y EXTERNAL -H ldapi:/// -f setdomain.ldif
```
```bash
SASL/EXTERNAL authentication started
SASL username: gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth
SASL SSF: 0
modifying entry "olcDatabase={1}monitor,cn=config"

modifying entry "olcDatabase={2}mdb,cn=config"

modifying entry "olcDatabase={2}mdb,cn=config"

modifying entry "olcDatabase={2}mdb,cn=config"

modifying entry "olcDatabase={2}mdb,cn=config"
```

```bash
ldapsearch -H ldap:// -x -s base -b "" -LLL "namingContexts"
```
```bash
dn:
namingContexts: dc=prolug,dc=lan
```
```bash
ldapadd -x -D cn=Manager,dc=prolug,dc=lan -W -f addou.ldif
```
```bash
Enter LDAP Password:
adding new entry "dc=prolug,dc=lan"

adding new entry "cn=Manager,dc=prolug,dc=lan"

adding new entry "ou=People,dc=prolug,dc=lan"

adding new entry "ou=Group,dc=prolug,dc=lan"
```
```bash
ldapsearch -H ldap:// -x -s base -b "" -LLL "+"
```
```bash
dn:
structuralObjectClass: OpenLDAProotDSE
configContext: cn=config
monitorContext: cn=Monitor
namingContexts: dc=prolug,dc=lan
supportedControl: 2.16.840.1.113730.3.4.18
supportedControl: 2.16.840.1.113730.3.4.2
supportedControl: 1.3.6.1.4.1.4203.1.10.1
supportedControl: 1.3.6.1.1.22
supportedControl: 1.2.840.113556.1.4.319
supportedControl: 1.2.826.0.1.3344810.2.3
supportedControl: 1.3.6.1.1.13.2
supportedControl: 1.3.6.1.1.13.1
supportedControl: 1.3.6.1.1.12
supportedExtension: 1.3.6.1.4.1.4203.1.11.1
supportedExtension: 1.3.6.1.4.1.4203.1.11.3
supportedExtension: 1.3.6.1.1.8
supportedExtension: 1.3.6.1.1.21.3
supportedExtension: 1.3.6.1.1.21.1
supportedFeatures: 1.3.6.1.1.14
supportedFeatures: 1.3.6.1.4.1.4203.1.5.1
supportedFeatures: 1.3.6.1.4.1.4203.1.5.2
supportedFeatures: 1.3.6.1.4.1.4203.1.5.3
supportedFeatures: 1.3.6.1.4.1.4203.1.5.4
supportedFeatures: 1.3.6.1.4.1.4203.1.5.5
supportedLDAPVersion: 3
entryDN:
subschemaSubentry: cn=Subschema
```
```bash
ldapsearch -x -b "dc=prolug,dc=lan" ou
```
```bash
# extended LDIF
#
# LDAPv3
# base <dc=prolug,dc=lan> with scope subtree
# filter: (objectclass=*)
# requesting: ou
#

# prolug.lan
dn: dc=prolug,dc=lan

# Manager, prolug.lan
dn: cn=Manager,dc=prolug,dc=lan

# People, prolug.lan
dn: ou=People,dc=prolug,dc=lan
ou: People

# Group, prolug.lan
dn: ou=Group,dc=prolug,dc=lan
ou: Group

# search result
search: 2
result: 0 Success

# numResponses: 5
# numEntries: 4
```
```bash
slappasswd
```
```bash
ldapadd -x -D cn=Manager,dc=prolug,dc=lan -W -f adduser.ldif
```
```bash
Enter LDAP Password:
adding new entry "uid=testuser,ou=People,dc=prolug,dc=lan"

adding new entry "cn=testuser,ou=Group,dc=prolug,dc=lan"
```
```bash
ldapsearch -x -b "ou=People,dc=prolug,dc=lan"
```
```bash
# extended LDIF
#
# LDAPv3
# base <ou=People,dc=prolug,dc=lan> with scope subtree
# filter: (objectclass=*)
# requesting: ALL
#

# People, prolug.lan
dn: ou=People,dc=prolug,dc=lan
objectClass: organizationalUnit
ou: People

# testuser, People, prolug.lan
dn: uid=testuser,ou=People,dc=prolug,dc=lan
objectClass: inetOrgPerson
objectClass: posixAccount
objectClass: shadowAccount
cn: testuser
sn: temp
loginShell: /bin/bash
uidNumber: 15000
gidNumber: 15000
homeDirectory: /home/testuser
shadowMax: 0
shadowWarning: 0
uid: testuser

# search result
search: 2
result: 0 Success

# numResponses: 3
# numEntries: 2
```
```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/pki/tls/ldapserver.key -out /etc/pki/tls/ldapserver.crt
```
```bash
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [XX]:
State or Province Name (full name) []:
Locality Name (eg, city) [Default City]:
Organization Name (eg, company) [Default Company Ltd]:
Organizational Unit Name (eg, section) []:
Common Name (eg, your name or your server's hostname) []:
Email Address []:
```
```bash
ls -l /etc/pki/tls/ldap*
```
```bash
-rw-r--r--. 1 ldap ldap 1237 Jun 14 18:09 /etc/pki/tls/ldapserver.crt
-rw-------. 1 ldap ldap 1708 Jun 14 18:09 /etc/pki/tls/ldapserver.key
```
```bash
ldapadd -Y EXTERNAL -H ldapi:/// -f tls.ldif
```
```bash
SASL/EXTERNAL authentication started
SASL username: gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth
SASL SSF: 0
modifying entry "cn=config"
```
```bash
dnf install openldap-clients sssd sssd-ldap oddjob-mkhomedir authselect
```
```bash
authselect select sssd with-mkhomedir --force
```
```bash
Backup stored at /var/lib/authselect/backups/2025-06-15-01-16-35.2lrC1f
Profile "sssd" was selected.
The following nsswitch maps are overwritten by the profile:
- passwd
- group
- netgroup
- automount
- services

Make sure that SSSD service is configured and enabled. See SSSD documentation for more information.

- with-mkhomedir is selected, make sure pam_oddjob_mkhomedir module
  is present and oddjobd service is enabled and active
  - systemctl enable --now oddjobd.service
```
```bash
systemctl status oddjobd.service
```
```bash
● oddjobd.service - privileged operations for unprivileged applications
     Loaded: loaded (/usr/lib/systemd/system/oddjobd.service; enabled; preset: disabled)
     Active: active (running) since Sat 2025-06-14 18:17:16 MST; 13s ago
   Main PID: 21723 (oddjobd)
      Tasks: 1 (limit: 24363)
     Memory: 548.0K
        CPU: 9ms
     CGroup: /system.slice/oddjobd.service
             └─21723 /usr/sbin/oddjobd -n -p /run/oddjobd.pid -t 300

Jun 14 18:17:16 hammer9 systemd[1]: Started privileged operations for unprivileged applications.
```
```bash
systemctl start sssd
```
```bash
● sssd.service - System Security Services Daemon
     Loaded: loaded (/usr/lib/systemd/system/sssd.service; enabled; preset: enabled)
     Active: active (running) since Sat 2025-06-14 18:23:07 MST; 7s ago
   Main PID: 21734 (sssd)
      Tasks: 5 (limit: 24363)
     Memory: 47.1M
        CPU: 290ms
     CGroup: /system.slice/sssd.service
             ├─21734 /usr/sbin/sssd -i --logger=files
             ├─21735 /usr/libexec/sssd/sssd_be --domain default --uid 0 --gid 0 --logger=files
             ├─21737 /usr/libexec/sssd/sssd_nss --uid 0 --gid 0 --logger=files
             ├─21738 /usr/libexec/sssd/sssd_pam --uid 0 --gid 0 --logger=files
             └─21739 /usr/libexec/sssd/sssd_autofs --uid 0 --gid 0 --logger=files

Jun 14 18:23:07 hammer9 systemd[1]: Starting System Security Services Daemon...
Jun 14 18:23:07 hammer9 sssd[21734]: Starting up
Jun 14 18:23:07 hammer9 sssd_be[21735]: Starting up
Jun 14 18:23:07 hammer9 sssd_nss[21737]: Starting up
Jun 14 18:23:07 hammer9 sssd_autofs[21739]: Starting up
Jun 14 18:23:07 hammer9 sssd_pam[21738]: Starting up
Jun 14 18:23:07 hammer9 systemd[1]: Started System Security Services Daemon.
```
```bash
id testuser
```
```bash
uid=15000(testuser) gid=15000(testuser) groups=15000(testuser)
```

