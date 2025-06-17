What file is fixed for all of them to be remediated?
```
httpd.conf
```
```bash
dnf install -y httpd
```
```bash
Last metadata expiration check: 1:39:15 ago on Mon Jun 16 09:47:23 2025.
Dependencies resolved.
================================================================================================================================================================================================================
 Package                                                Architecture                                Version                                                Repository                                      Size
================================================================================================================================================================================================================
Installing:
 httpd                                                  x86_64                                      2.4.62-4.el9                                           appstream                                       45 k
Installing dependencies:
 apr                                                    x86_64                                      1.7.0-12.el9_3                                         appstream                                      122 k
 apr-util                                               x86_64                                      1.6.1-23.el9                                           appstream                                       94 k
 apr-util-bdb                                           x86_64                                      1.6.1-23.el9                                           appstream                                       12 k
 httpd-core                                             x86_64                                      2.4.62-4.el9                                           appstream                                      1.4 M
 httpd-filesystem                                       noarch                                      2.4.62-4.el9                                           appstream                                       12 k
 httpd-tools                                            x86_64                                      2.4.62-4.el9                                           appstream                                       78 k
 mailcap                                                noarch                                      2.1.49-5.el9                                           baseos                                          32 k
 rocky-logos-httpd                                      noarch                                      90.16-1.el9                                            appstream                                       24 k
Installing weak dependencies:
 apr-util-openssl                                       x86_64                                      1.6.1-23.el9                                           appstream                                       14 k
 mod_http2                                              x86_64                                      2.0.26-4.el9                                           appstream                                      163 k
 mod_lua                                                x86_64                                      2.4.62-4.el9                                           appstream                                       58 k

Transaction Summary
================================================================================================================================================================================================================
Install  12 Packages

Total download size: 2.0 M
Installed size: 6.1 M
Downloading Packages:
(1/12): apr-util-bdb-1.6.1-23.el9.x86_64.rpm                                                                                                                                     44 kB/s |  12 kB     00:00
(2/12): httpd-2.4.62-4.el9.x86_64.rpm                                                                                                                                           104 kB/s |  45 kB     00:00
(3/12): mailcap-2.1.49-5.el9.noarch.rpm                                                                                                                                          71 kB/s |  32 kB     00:00
(4/12): apr-util-1.6.1-23.el9.x86_64.rpm                                                                                                                                        575 kB/s |  94 kB     00:00
(5/12): httpd-tools-2.4.62-4.el9.x86_64.rpm                                                                                                                                     936 kB/s |  78 kB     00:00
(6/12): rocky-logos-httpd-90.16-1.el9.noarch.rpm                                                                                                                                 99 kB/s |  24 kB     00:00
(7/12): mod_http2-2.0.26-4.el9.x86_64.rpm                                                                                                                                       1.9 MB/s | 163 kB     00:00
(8/12): apr-util-openssl-1.6.1-23.el9.x86_64.rpm                                                                                                                                184 kB/s |  14 kB     00:00
(9/12): mod_lua-2.4.62-4.el9.x86_64.rpm                                                                                                                                         373 kB/s |  58 kB     00:00
(10/12): httpd-core-2.4.62-4.el9.x86_64.rpm                                                                                                                                     2.1 MB/s | 1.4 MB     00:00
(11/12): httpd-filesystem-2.4.62-4.el9.noarch.rpm                                                                                                                               146 kB/s |  12 kB     00:00
(12/12): apr-1.7.0-12.el9_3.x86_64.rpm                                                                                                                                          1.4 MB/s | 122 kB     00:00
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                           1.6 MB/s | 2.0 MB     00:01
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                        1/1
  Installing       : apr-1.7.0-12.el9_3.x86_64                                                                                                                                                             1/12
  Installing       : apr-util-openssl-1.6.1-23.el9.x86_64                                                                                                                                                  2/12
  Installing       : apr-util-1.6.1-23.el9.x86_64                                                                                                                                                          3/12
  Installing       : apr-util-bdb-1.6.1-23.el9.x86_64                                                                                                                                                      4/12
  Installing       : httpd-tools-2.4.62-4.el9.x86_64                                                                                                                                                       5/12
  Running scriptlet: httpd-filesystem-2.4.62-4.el9.noarch                                                                                                                                                  6/12
  Installing       : httpd-filesystem-2.4.62-4.el9.noarch                                                                                                                                                  6/12
  Installing       : rocky-logos-httpd-90.16-1.el9.noarch                                                                                                                                                  7/12
  Installing       : mailcap-2.1.49-5.el9.noarch                                                                                                                                                           8/12
  Installing       : httpd-core-2.4.62-4.el9.x86_64                                                                                                                                                        9/12
  Installing       : mod_lua-2.4.62-4.el9.x86_64                                                                                                                                                          10/12
  Installing       : mod_http2-2.0.26-4.el9.x86_64                                                                                                                                                        11/12
  Installing       : httpd-2.4.62-4.el9.x86_64                                                                                                                                                            12/12
  Running scriptlet: httpd-2.4.62-4.el9.x86_64                                                                                                                                                            12/12
  Verifying        : mailcap-2.1.49-5.el9.noarch                                                                                                                                                           1/12
  Verifying        : apr-util-bdb-1.6.1-23.el9.x86_64                                                                                                                                                      2/12
  Verifying        : httpd-2.4.62-4.el9.x86_64                                                                                                                                                             3/12
  Verifying        : httpd-core-2.4.62-4.el9.x86_64                                                                                                                                                        4/12
  Verifying        : apr-util-1.6.1-23.el9.x86_64                                                                                                                                                          5/12
  Verifying        : rocky-logos-httpd-90.16-1.el9.noarch                                                                                                                                                  6/12
  Verifying        : httpd-tools-2.4.62-4.el9.x86_64                                                                                                                                                       7/12
  Verifying        : mod_http2-2.0.26-4.el9.x86_64                                                                                                                                                         8/12
  Verifying        : mod_lua-2.4.62-4.el9.x86_64                                                                                                                                                           9/12
  Verifying        : apr-util-openssl-1.6.1-23.el9.x86_64                                                                                                                                                 10/12
  Verifying        : apr-1.7.0-12.el9_3.x86_64                                                                                                                                                            11/12
  Verifying        : httpd-filesystem-2.4.62-4.el9.noarch                                                                                                                                                 12/12

Installed:
  apr-1.7.0-12.el9_3.x86_64            apr-util-1.6.1-23.el9.x86_64    apr-util-bdb-1.6.1-23.el9.x86_64 apr-util-openssl-1.6.1-23.el9.x86_64 httpd-2.4.62-4.el9.x86_64   httpd-core-2.4.62-4.el9.x86_64
  httpd-filesystem-2.4.62-4.el9.noarch httpd-tools-2.4.62-4.el9.x86_64 mailcap-2.1.49-5.el9.noarch      mod_http2-2.0.26-4.el9.x86_64        mod_lua-2.4.62-4.el9.x86_64 rocky-logos-httpd-90.16-1.el9.noarch

Complete!
```
- Check STIG V-214234
    
    - What is the problem
		The Apache web server must use a logging mechanism that is configured to alert the Information System Security Officer (ISSO) and System Administrator (SA) in the event of a processing failure.
        
    - What is the fix?
        Work with the SIEM administrator to configure an alert when no audit data is received from Apache based on the defined schedule of connections.
    - What type of control is being implemented?
        
    - Is it set properly on your system?
        
- Check STIG V-214248
    
    - What is the problem?
        Apache web server application directories, libraries, and configuration files must only be accessible to privileged users.
    - What is the fix?
		Ensure non-administrators are not allowed access to the directory tree, the shell, or other operating system functions and utilities.
    - What type of control is being implemented?
        
    - Is it set properly on your system?
        
    - How do you think SELINUX will help implement this control in an enforcing state? Or will it not affect it? 
	    -SELinux can prevent access to the files and directory to users and processes by checking the labels that are defined and take action.

```bash
cd /etc/yum.repos.d
mkdir old_archive
mv *.repo old_archive
dnf repolist
```
```bash
No repositories available
```
```bash
mount -o loop /lab_work/repos_and_patching/Rocky-9.5-x86_64-dvd.iso /mnt
df -h  # Should see the mount point
ls -l /mnt
touch /etc/yum.repos.d/rocky9.repo
vi /etc/yum.repos.d/rocky9.repo
```
```bash
chmod 644 /etc/yum.repos.d/rocky9.repo
dnf clean all
```
```bash
41 files removed
```
```bash
dnf repolist
dnf --disablerepo="*" --enablerepo="AppStream" list available
```
```bash
5591
```
```bash
dnf --disablerepo="*" --enablerepo="BaseOS" list available
```
```bash
1002
```
```bash
dnf --disablerepo="*" --enablerepo="BaseOS AppStream" install gimp
```
1. How many packages does it want to install?
```bash
	Install  173 Packages
```

1. How can you tell they're from different repos?
	4th column indicates the provenance, AppStream & BaseOS

```bash
rpm -qa | grep -i httpd
httpd-tools-2.4.62-4.el9.x86_64
httpd-filesystem-2.4.62-4.el9.noarch
rocky-logos-httpd-90.16-1.el9.noarch
httpd-core-2.4.62-4.el9.x86_64
httpd-2.4.62-4.el9.x86_64

systemctl status httpd
● httpd.service - The Apache HTTP Server
     Loaded: loaded (/usr/lib/systemd/system/httpd.service; disabled; preset: disabled)
     Active: active (running) since Mon 2025-06-16 11:27:59 MST; 26min ago
       Docs: man:httpd.service(8)
   Main PID: 11615 (httpd)
     Status: "Total requests: 0; Idle/Busy workers 100/0;Requests/sec: 0; Bytes served/sec:   0 B/sec"
      Tasks: 177 (limit: 24363)
     Memory: 21.7M
        CPU: 1.836s
     CGroup: /system.slice/httpd.service
             ├─11615 /usr/sbin/httpd -DFOREGROUND
             ├─11616 /usr/sbin/httpd -DFOREGROUND
             ├─11617 /usr/sbin/httpd -DFOREGROUND
             ├─11618 /usr/sbin/httpd -DFOREGROUND
             └─11619 /usr/sbin/httpd -DFOREGROUND

Jun 16 11:27:58 hammer9 systemd[1]: Starting The Apache HTTP Server...
Jun 16 11:27:58 hammer9 httpd[11615]: AH00558: httpd: Could not reliably determine the server's fully qualified domain name, using 192.168.200.159. Set the 'ServerName' directive globally to suppress this me>
Jun 16 11:27:59 hammer9 httpd[11615]: Server configured, listening on: port 80
Jun 16 11:27:59 hammer9 systemd[1]: Started The Apache HTTP Server.
[root@hammer9 yum.repos.d]# ss -ntulp | grep 80
tcp   LISTEN 0      4096         0.0.0.0:111       0.0.0.0:*    users:(("rpcbind",pid=687,fd=4),("systemd",pid=1,fd=80))
tcp   LISTEN 0      511                *:80              *:*    users:(("httpd",pid=11619,fd=4),("httpd",pid=11618,fd=4),("httpd",pid=11617,fd=4),("httpd",pid=11615,fd=4))

lsof -i :80
COMMAND   PID   USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
httpd   11615   root    4u  IPv6  43729      0t0  TCP *:http (LISTEN)
httpd   11617 apache    4u  IPv6  43729      0t0  TCP *:http (LISTEN)
httpd   11618 apache    4u  IPv6  43729      0t0  TCP *:http (LISTEN)
httpd   11619 apache    4u  IPv6  43729      0t0  TCP *:http (LISTEN)
```
```bash
dnf clean all
17 files removed
```
```bash
dnf repolist
repo id                                                                                      repo name
AppStream                                                                                    AppStream Packages Rocky Linux 9
BaseOS                                                                                       BaseOS Packages Rocky Linux 9
```


```bash
ansible-playbook -v -i /root/HPC_Deploy/hosts 03_package_update_or_install.yaml --extra-vars "action=install"
Using /root/HPC_Deploy/ansible.cfg as config file
[WARNING]: Found variable using reserved name: action

PLAY [all] ********************************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [controlplane]
ok: [node01]

TASK [packages_install : Debug env variables just to see them] ****************************************************************************************************************************
ok: [controlplane] => 
  app: web
ok: [node01] => 
  app: db

TASK [packages_install : Install apache2 on the web server] *******************************************************************************************************************************
skipping: [node01] => changed=false 
  false_condition: '"web" in app'
  skip_reason: Conditional result was False
changed: [controlplane] => changed=true 
  cache_update_time: 1750099275
  cache_updated: false
  stderr: ''
  stderr_lines: <omitted>
  stdout: |-
    Reading package lists...
    Building dependency tree...
    Reading state information...
    The following additional packages will be installed:
      apache2-bin apache2-data apache2-utils libapache2-mod-php8.3 libapr1t64
      libaprutil1-dbd-sqlite3 libaprutil1-ldap libaprutil1t64 liblua5.4-0 php8.3
    Suggested packages:
      apache2-doc apache2-suexec-pristine | apache2-suexec-custom php-pear
    The following NEW packages will be installed:
      apache2 apache2-bin apache2-data apache2-utils libapache2-mod-php8.3
      libapr1t64 libaprutil1-dbd-sqlite3 libaprutil1-ldap libaprutil1t64
      liblua5.4-0 php php8.3
    0 upgraded, 12 newly installed, 0 to remove and 152 not upgraded.
    Need to get 3929 kB of archives.
    After this operation, 13.8 MB of additional disk space will be used.
    Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libapr1t64 amd64 1.7.2-3.1ubuntu0.1 [108 kB]
    Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1t64 amd64 1.6.3-1.1ubuntu7 [91.9 kB]
    Get:3 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1-dbd-sqlite3 amd64 1.6.3-1.1ubuntu7 [11.2 kB]
    Get:4 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1-ldap amd64 1.6.3-1.1ubuntu7 [9116 B]
    Get:5 http://archive.ubuntu.com/ubuntu noble/main amd64 liblua5.4-0 amd64 5.4.6-3build2 [166 kB]
    Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-bin amd64 2.4.58-1ubuntu8.6 [1330 kB]
    Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-data all 2.4.58-1ubuntu8.6 [163 kB]
    Get:8 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-utils amd64 2.4.58-1ubuntu8.6 [97.2 kB]
    Get:9 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2 amd64 2.4.58-1ubuntu8.6 [90.2 kB]
    Get:10 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libapache2-mod-php8.3 amd64 8.3.6-0ubuntu0.24.04.4 [1850 kB]
    Get:11 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3 all 8.3.6-0ubuntu0.24.04.4 [9172 B]
    Get:12 http://archive.ubuntu.com/ubuntu noble/main amd64 php all 2:8.3+93ubuntu2 [4076 B]
    Fetched 3929 kB in 0s (13.2 MB/s)
    Selecting previously unselected package libapr1t64:amd64.
    (Reading database ... (Reading database ... 5%(Reading database ... 10%(Reading database ... 15%(Reading database ... 20%(Reading database ... 25%(Reading database ... 30%(Reading database ... 35%(Reading database ... 40%(Reading database ... 45%(Reading database ... 50%(Reading database ... 55%(Reading database ... 60%(Reading database ... 65%(Reading database ... 70%(Reading database ... 75%(Reading database ... 80%(Reading database ... 85%(Reading database ... 90%(Reading database ... 95%(Reading database ... 100%(Reading database ... 162894 files and directories currently installed.)
    Preparing to unpack .../00-libapr1t64_1.7.2-3.1ubuntu0.1_amd64.deb ...
    Unpacking libapr1t64:amd64 (1.7.2-3.1ubuntu0.1) ...
    Selecting previously unselected package libaprutil1t64:amd64.
    Preparing to unpack .../01-libaprutil1t64_1.6.3-1.1ubuntu7_amd64.deb ...
    Unpacking libaprutil1t64:amd64 (1.6.3-1.1ubuntu7) ...
    Selecting previously unselected package libaprutil1-dbd-sqlite3:amd64.
    Preparing to unpack .../02-libaprutil1-dbd-sqlite3_1.6.3-1.1ubuntu7_amd64.deb ...
    Unpacking libaprutil1-dbd-sqlite3:amd64 (1.6.3-1.1ubuntu7) ...
    Selecting previously unselected package libaprutil1-ldap:amd64.
    Preparing to unpack .../03-libaprutil1-ldap_1.6.3-1.1ubuntu7_amd64.deb ...
    Unpacking libaprutil1-ldap:amd64 (1.6.3-1.1ubuntu7) ...
    Selecting previously unselected package liblua5.4-0:amd64.
    Preparing to unpack .../04-liblua5.4-0_5.4.6-3build2_amd64.deb ...
    Unpacking liblua5.4-0:amd64 (5.4.6-3build2) ...
    Selecting previously unselected package apache2-bin.
    Preparing to unpack .../05-apache2-bin_2.4.58-1ubuntu8.6_amd64.deb ...
    Unpacking apache2-bin (2.4.58-1ubuntu8.6) ...
    Selecting previously unselected package apache2-data.
    Preparing to unpack .../06-apache2-data_2.4.58-1ubuntu8.6_all.deb ...
    Unpacking apache2-data (2.4.58-1ubuntu8.6) ...
    Selecting previously unselected package apache2-utils.
    Preparing to unpack .../07-apache2-utils_2.4.58-1ubuntu8.6_amd64.deb ...
    Unpacking apache2-utils (2.4.58-1ubuntu8.6) ...
    Selecting previously unselected package apache2.
    Preparing to unpack .../08-apache2_2.4.58-1ubuntu8.6_amd64.deb ...
    Unpacking apache2 (2.4.58-1ubuntu8.6) ...
    Selecting previously unselected package libapache2-mod-php8.3.
    Preparing to unpack .../09-libapache2-mod-php8.3_8.3.6-0ubuntu0.24.04.4_amd64.deb ...
    Unpacking libapache2-mod-php8.3 (8.3.6-0ubuntu0.24.04.4) ...
    Selecting previously unselected package php8.3.
    Preparing to unpack .../10-php8.3_8.3.6-0ubuntu0.24.04.4_all.deb ...
    Unpacking php8.3 (8.3.6-0ubuntu0.24.04.4) ...
    Selecting previously unselected package php.
    Preparing to unpack .../11-php_2%3a8.3+93ubuntu2_all.deb ...
    Unpacking php (2:8.3+93ubuntu2) ...
    Setting up libapr1t64:amd64 (1.7.2-3.1ubuntu0.1) ...
    Setting up liblua5.4-0:amd64 (5.4.6-3build2) ...
    Setting up apache2-data (2.4.58-1ubuntu8.6) ...
    Setting up libaprutil1t64:amd64 (1.6.3-1.1ubuntu7) ...
    Setting up libaprutil1-ldap:amd64 (1.6.3-1.1ubuntu7) ...
    Setting up libaprutil1-dbd-sqlite3:amd64 (1.6.3-1.1ubuntu7) ...
    Setting up apache2-utils (2.4.58-1ubuntu8.6) ...
    Setting up apache2-bin (2.4.58-1ubuntu8.6) ...
    Setting up libapache2-mod-php8.3 (8.3.6-0ubuntu0.24.04.4) ...
    Package apache2 is not configured yet. Will defer actions by package libapache2-mod-php8.3.
  
    Creating config file /etc/php/8.3/apache2/php.ini with new version
    No module matches
    Setting up apache2 (2.4.58-1ubuntu8.6) ...
    Enabling module mpm_event.
    Enabling module authz_core.
    Enabling module authz_host.
    Enabling module authn_core.
    Enabling module auth_basic.
    Enabling module access_compat.
    Enabling module authn_file.
    Enabling module authz_user.
    Enabling module alias.
    Enabling module dir.
    Enabling module autoindex.
    Enabling module env.
    Enabling module mime.
    Enabling module negotiation.
    Enabling module setenvif.
    Enabling module filter.
    Enabling module deflate.
    Enabling module status.
    Enabling module reqtimeout.
    Enabling conf charset.
    Enabling conf localized-error-pages.
    Enabling conf other-vhosts-access-log.
    Enabling conf security.
    Enabling conf serve-cgi-bin.
    Enabling site 000-default.
    info: Switch to mpm prefork for package libapache2-mod-php8.3
    Module mpm_event disabled.
    Enabling module mpm_prefork.
    info: Executing deferred 'a2enmod php8.3' for package libapache2-mod-php8.3
    Enabling module php8.3.
    Created symlink /etc/systemd/system/multi-user.target.wants/apache2.service → /usr/lib/systemd/system/apache2.service.
    Created symlink /etc/systemd/system/multi-user.target.wants/apache-htcacheclean.service → /usr/lib/systemd/system/apache-htcacheclean.service.
    Setting up php8.3 (8.3.6-0ubuntu0.24.04.4) ...
    Setting up php (2:8.3+93ubuntu2) ...
    Processing triggers for ufw (0.36.2-6) ...
    Processing triggers for man-db (2.12.0-4build2) ...
    Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
    Processing triggers for libapache2-mod-php8.3 (8.3.6-0ubuntu0.24.04.4) ...
  
    Running kernel seems to be up-to-date.
  
    No services need to be restarted.
  
    No containers need to be restarted.
  
    No user sessions are running outdated binaries.
  
    No VM guests are running outdated hypervisor (qemu) binaries on this host.
  stdout_lines: <omitted>

TASK [packages_install : Install mariadb on the web server] *******************************************************************************************************************************
skipping: [controlplane] => changed=false 
  false_condition: '"db" in app'
  skip_reason: Conditional result was False
changed: [node01] => changed=true 
  cache_update_time: 1750099295
  cache_updated: false
  stderr: ''
  stderr_lines: <omitted>
  stdout: |-
    Reading package lists...
    Building dependency tree...
    Reading state information...
    The following package was automatically installed and is no longer required:
      squashfs-tools
    Use 'apt autoremove' to remove it.
    The following additional packages will be installed:
      galera-4 libcgi-fast-perl libcgi-pm-perl libclone-perl
      libconfig-inifiles-perl libdbd-mysql-perl libdbi-perl libencode-locale-perl
      libfcgi-bin libfcgi-perl libfcgi0t64 libhtml-parser-perl libhtml-tagset-perl
      libhtml-template-perl libhttp-date-perl libhttp-message-perl libio-html-perl
      liblwp-mediatypes-perl libmariadb3 libmysqlclient21 libsnappy1v5
      libtimedate-perl liburi-perl liburing2 mariadb-client-core mariadb-common
      mariadb-plugin-provider-bzip2 mariadb-plugin-provider-lz4
      mariadb-plugin-provider-lzma mariadb-plugin-provider-lzo
      mariadb-plugin-provider-snappy mariadb-server-core mysql-common pv socat
    Suggested packages:
      libmldbm-perl libnet-daemon-perl libsql-statement-perl libdata-dump-perl
      libipc-sharedcache-perl libio-compress-brotli-perl libbusiness-isbn-perl
      libregexp-ipv6-perl libwww-perl mailx mariadb-test doc-base
    The following NEW packages will be installed:
      galera-4 libcgi-fast-perl libcgi-pm-perl libclone-perl
      libconfig-inifiles-perl libdbd-mysql-perl libdbi-perl libencode-locale-perl
      libfcgi-bin libfcgi-perl libfcgi0t64 libhtml-parser-perl libhtml-tagset-perl
      libhtml-template-perl libhttp-date-perl libhttp-message-perl libio-html-perl
      liblwp-mediatypes-perl libmariadb3 libmysqlclient21 libsnappy1v5
      libtimedate-perl liburi-perl liburing2 mariadb-client mariadb-client-core
      mariadb-common mariadb-plugin-provider-bzip2 mariadb-plugin-provider-lz4
      mariadb-plugin-provider-lzma mariadb-plugin-provider-lzo
      mariadb-plugin-provider-snappy mariadb-server mariadb-server-core
      mysql-common pv socat
    0 upgraded, 37 newly installed, 0 to remove and 170 not upgraded.
    Need to get 19.7 MB of archives.
    After this operation, 201 MB of additional disk space will be used.
    Get:1 http://archive.ubuntu.com/ubuntu noble/universe amd64 galera-4 amd64 26.4.16-2build4 [736 kB]
    Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 mysql-common all 5.8+1.1.0build1 [6746 B]
    Get:3 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-common all 1:10.11.13-0ubuntu0.24.04.1 [28.3 kB]
    Get:4 http://archive.ubuntu.com/ubuntu noble/main amd64 libdbi-perl amd64 1.643-4build3 [721 kB]
    Get:5 http://archive.ubuntu.com/ubuntu noble/main amd64 libconfig-inifiles-perl all 3.000003-2 [39.4 kB]
    Get:6 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 libmariadb3 amd64 1:10.11.13-0ubuntu0.24.04.1 [196 kB]
    Get:7 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-client-core amd64 1:10.11.13-0ubuntu0.24.04.1 [1037 kB]
    Get:8 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-client amd64 1:10.11.13-0ubuntu0.24.04.1 [2500 kB]
    Get:9 http://archive.ubuntu.com/ubuntu noble/main amd64 liburing2 amd64 2.5-1build1 [21.1 kB]
    Get:10 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-server-core amd64 1:10.11.13-0ubuntu0.24.04.1 [8392 kB]
    Get:11 http://archive.ubuntu.com/ubuntu noble/main amd64 socat amd64 1.8.0.0-4build3 [374 kB]
    Get:12 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-server amd64 1:10.11.13-0ubuntu0.24.04.1 [3464 kB]
    Get:13 http://archive.ubuntu.com/ubuntu noble/main amd64 libhtml-tagset-perl all 3.20-6 [11.3 kB]
    Get:14 http://archive.ubuntu.com/ubuntu noble/main amd64 liburi-perl all 5.27-1 [88.0 kB]
    Get:15 http://archive.ubuntu.com/ubuntu noble/main amd64 libhtml-parser-perl amd64 3.81-1build3 [85.8 kB]
    Get:16 http://archive.ubuntu.com/ubuntu noble/main amd64 libcgi-pm-perl all 4.63-1 [185 kB]
    Get:17 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libfcgi0t64 amd64 2.4.2-2.1ubuntu0.24.04.1 [27.0 kB]
    Get:18 http://archive.ubuntu.com/ubuntu noble/main amd64 libfcgi-perl amd64 0.82+ds-3build2 [21.7 kB]
    Get:19 http://archive.ubuntu.com/ubuntu noble/main amd64 libcgi-fast-perl all 1:2.17-1 [10.3 kB]
    Get:20 http://archive.ubuntu.com/ubuntu noble/main amd64 libclone-perl amd64 0.46-1build3 [10.7 kB]
    Get:21 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libmysqlclient21 amd64 8.0.42-0ubuntu0.24.04.1 [1254 kB]
    Get:22 http://archive.ubuntu.com/ubuntu noble/universe amd64 libdbd-mysql-perl amd64 4.052-1ubuntu3 [85.5 kB]
    Get:23 http://archive.ubuntu.com/ubuntu noble/main amd64 libencode-locale-perl all 1.05-3 [11.6 kB]
    Get:24 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libfcgi-bin amd64 2.4.2-2.1ubuntu0.24.04.1 [11.2 kB]
    Get:25 http://archive.ubuntu.com/ubuntu noble/main amd64 libhtml-template-perl all 2.97-2 [60.2 kB]
    Get:26 http://archive.ubuntu.com/ubuntu noble/main amd64 libtimedate-perl all 2.3300-2 [34.0 kB]
    Get:27 http://archive.ubuntu.com/ubuntu noble/main amd64 libhttp-date-perl all 6.06-1 [10.2 kB]
    Get:28 http://archive.ubuntu.com/ubuntu noble/main amd64 libio-html-perl all 1.004-3 [15.9 kB]
    Get:29 http://archive.ubuntu.com/ubuntu noble/main amd64 liblwp-mediatypes-perl all 6.04-2 [20.1 kB]
    Get:30 http://archive.ubuntu.com/ubuntu noble/main amd64 libhttp-message-perl all 6.45-1ubuntu1 [78.2 kB]
    Get:31 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-bzip2 amd64 1:10.11.13-0ubuntu0.24.04.1 [13.9 kB]
    Get:32 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-lz4 amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
    Get:33 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-lzma amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
    Get:34 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-lzo amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
    Get:35 http://archive.ubuntu.com/ubuntu noble/main amd64 libsnappy1v5 amd64 1.1.10-1build1 [28.6 kB]
    Get:36 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-snappy amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
    Get:37 http://archive.ubuntu.com/ubuntu noble/main amd64 pv amd64 1.8.5-2build1 [73.9 kB]
    Preconfiguring packages ...
    Fetched 19.7 MB in 7s (2819 kB/s)
    Selecting previously unselected package galera-4.
    (Reading database ... (Reading database ... 5%(Reading database ... 10%(Reading database ... 15%(Reading database ... 20%(Reading database ... 25%(Reading database ... 30%(Reading database ... 35%(Reading database ... 40%(Reading database ... 45%(Reading database ... 50%(Reading database ... 55%(Reading database ... 60%(Reading database ... 65%(Reading database ... 70%(Reading database ... 75%(Reading database ... 80%(Reading database ... 85%(Reading database ... 90%(Reading database ... 95%(Reading database ... 100%(Reading database ... 82216 files and directories currently installed.)
    Preparing to unpack .../00-galera-4_26.4.16-2build4_amd64.deb ...
    info: The home dir /nonexistent you specified can't be accessed: No such file or directory
  
    info: Selecting UID from range 100 to 999 ...
  
    info: Adding system user `_galera' (UID 109) ...
    info: Adding new user `_galera' (UID 109) with group `nogroup' ...
    info: Not creating `/nonexistent'.
    Unpacking galera-4 (26.4.16-2build4) ...
    Selecting previously unselected package mysql-common.
    Preparing to unpack .../01-mysql-common_5.8+1.1.0build1_all.deb ...
    Unpacking mysql-common (5.8+1.1.0build1) ...
    Selecting previously unselected package mariadb-common.
    Preparing to unpack .../02-mariadb-common_1%3a10.11.13-0ubuntu0.24.04.1_all.deb ...
    Unpacking mariadb-common (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package libdbi-perl:amd64.
    Preparing to unpack .../03-libdbi-perl_1.643-4build3_amd64.deb ...
    Unpacking libdbi-perl:amd64 (1.643-4build3) ...
    Selecting previously unselected package libconfig-inifiles-perl.
    Preparing to unpack .../04-libconfig-inifiles-perl_3.000003-2_all.deb ...
    Unpacking libconfig-inifiles-perl (3.000003-2) ...
    Selecting previously unselected package libmariadb3:amd64.
    Preparing to unpack .../05-libmariadb3_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking libmariadb3:amd64 (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package mariadb-client-core.
    Preparing to unpack .../06-mariadb-client-core_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-client-core (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package mariadb-client.
    Preparing to unpack .../07-mariadb-client_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-client (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package liburing2:amd64.
    Preparing to unpack .../08-liburing2_2.5-1build1_amd64.deb ...
    Unpacking liburing2:amd64 (2.5-1build1) ...
    Selecting previously unselected package mariadb-server-core.
    Preparing to unpack .../09-mariadb-server-core_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-server-core (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package socat.
    Preparing to unpack .../10-socat_1.8.0.0-4build3_amd64.deb ...
    Unpacking socat (1.8.0.0-4build3) ...
    Setting up mysql-common (5.8+1.1.0build1) ...
    update-alternatives: using /etc/mysql/my.cnf.fallback to provide /etc/mysql/my.cnf (my.cnf) in auto mode
    Setting up mariadb-common (1:10.11.13-0ubuntu0.24.04.1) ...
    update-alternatives: using /etc/mysql/mariadb.cnf to provide /etc/mysql/my.cnf (my.cnf) in auto mode
    Selecting previously unselected package mariadb-server.
    (Reading database ... (Reading database ... 5%(Reading database ... 10%(Reading database ... 15%(Reading database ... 20%(Reading database ... 25%(Reading database ... 30%(Reading database ... 35%(Reading database ... 40%(Reading database ... 45%(Reading database ... 50%(Reading database ... 55%(Reading database ... 60%(Reading database ... 65%(Reading database ... 70%(Reading database ... 75%(Reading database ... 80%(Reading database ... 85%(Reading database ... 90%(Reading database ... 95%(Reading database ... 100%(Reading database ... 82690 files and directories currently installed.)
    Preparing to unpack .../00-mariadb-server_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-server (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package libhtml-tagset-perl.
    Preparing to unpack .../01-libhtml-tagset-perl_3.20-6_all.deb ...
    Unpacking libhtml-tagset-perl (3.20-6) ...
    Selecting previously unselected package liburi-perl.
    Preparing to unpack .../02-liburi-perl_5.27-1_all.deb ...
    Unpacking liburi-perl (5.27-1) ...
    Selecting previously unselected package libhtml-parser-perl:amd64.
    Preparing to unpack .../03-libhtml-parser-perl_3.81-1build3_amd64.deb ...
    Unpacking libhtml-parser-perl:amd64 (3.81-1build3) ...
    Selecting previously unselected package libcgi-pm-perl.
    Preparing to unpack .../04-libcgi-pm-perl_4.63-1_all.deb ...
    Unpacking libcgi-pm-perl (4.63-1) ...
    Selecting previously unselected package libfcgi0t64:amd64.
    Preparing to unpack .../05-libfcgi0t64_2.4.2-2.1ubuntu0.24.04.1_amd64.deb ...
    Unpacking libfcgi0t64:amd64 (2.4.2-2.1ubuntu0.24.04.1) ...
    Selecting previously unselected package libfcgi-perl.
    Preparing to unpack .../06-libfcgi-perl_0.82+ds-3build2_amd64.deb ...
    Unpacking libfcgi-perl (0.82+ds-3build2) ...
    Selecting previously unselected package libcgi-fast-perl.
    Preparing to unpack .../07-libcgi-fast-perl_1%3a2.17-1_all.deb ...
    Unpacking libcgi-fast-perl (1:2.17-1) ...
    Selecting previously unselected package libclone-perl:amd64.
    Preparing to unpack .../08-libclone-perl_0.46-1build3_amd64.deb ...
    Unpacking libclone-perl:amd64 (0.46-1build3) ...
    Selecting previously unselected package libmysqlclient21:amd64.
    Preparing to unpack .../09-libmysqlclient21_8.0.42-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking libmysqlclient21:amd64 (8.0.42-0ubuntu0.24.04.1) ...
    Selecting previously unselected package libdbd-mysql-perl:amd64.
    Preparing to unpack .../10-libdbd-mysql-perl_4.052-1ubuntu3_amd64.deb ...
    Unpacking libdbd-mysql-perl:amd64 (4.052-1ubuntu3) ...
    Selecting previously unselected package libencode-locale-perl.
    Preparing to unpack .../11-libencode-locale-perl_1.05-3_all.deb ...
    Unpacking libencode-locale-perl (1.05-3) ...
    Selecting previously unselected package libfcgi-bin.
    Preparing to unpack .../12-libfcgi-bin_2.4.2-2.1ubuntu0.24.04.1_amd64.deb ...
    Unpacking libfcgi-bin (2.4.2-2.1ubuntu0.24.04.1) ...
    Selecting previously unselected package libhtml-template-perl.
    Preparing to unpack .../13-libhtml-template-perl_2.97-2_all.deb ...
    Unpacking libhtml-template-perl (2.97-2) ...
    Selecting previously unselected package libtimedate-perl.
    Preparing to unpack .../14-libtimedate-perl_2.3300-2_all.deb ...
    Unpacking libtimedate-perl (2.3300-2) ...
    Selecting previously unselected package libhttp-date-perl.
    Preparing to unpack .../15-libhttp-date-perl_6.06-1_all.deb ...
    Unpacking libhttp-date-perl (6.06-1) ...
    Selecting previously unselected package libio-html-perl.
    Preparing to unpack .../16-libio-html-perl_1.004-3_all.deb ...
    Unpacking libio-html-perl (1.004-3) ...
    Selecting previously unselected package liblwp-mediatypes-perl.
    Preparing to unpack .../17-liblwp-mediatypes-perl_6.04-2_all.deb ...
    Unpacking liblwp-mediatypes-perl (6.04-2) ...
    Selecting previously unselected package libhttp-message-perl.
    Preparing to unpack .../18-libhttp-message-perl_6.45-1ubuntu1_all.deb ...
    Unpacking libhttp-message-perl (6.45-1ubuntu1) ...
    Selecting previously unselected package mariadb-plugin-provider-bzip2.
    Preparing to unpack .../19-mariadb-plugin-provider-bzip2_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-plugin-provider-bzip2 (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package mariadb-plugin-provider-lz4.
    Preparing to unpack .../20-mariadb-plugin-provider-lz4_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-plugin-provider-lz4 (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package mariadb-plugin-provider-lzma.
    Preparing to unpack .../21-mariadb-plugin-provider-lzma_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-plugin-provider-lzma (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package mariadb-plugin-provider-lzo.
    Preparing to unpack .../22-mariadb-plugin-provider-lzo_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-plugin-provider-lzo (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package libsnappy1v5:amd64.
    Preparing to unpack .../23-libsnappy1v5_1.1.10-1build1_amd64.deb ...
    Unpacking libsnappy1v5:amd64 (1.1.10-1build1) ...
    Selecting previously unselected package mariadb-plugin-provider-snappy.
    Preparing to unpack .../24-mariadb-plugin-provider-snappy_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
    Unpacking mariadb-plugin-provider-snappy (1:10.11.13-0ubuntu0.24.04.1) ...
    Selecting previously unselected package pv.
    Preparing to unpack .../25-pv_1.8.5-2build1_amd64.deb ...
    Unpacking pv (1.8.5-2build1) ...
    Setting up libconfig-inifiles-perl (3.000003-2) ...
    Setting up galera-4 (26.4.16-2build4) ...
    Setting up libmysqlclient21:amd64 (8.0.42-0ubuntu0.24.04.1) ...
    Setting up libclone-perl:amd64 (0.46-1build3) ...
    Setting up libfcgi0t64:amd64 (2.4.2-2.1ubuntu0.24.04.1) ...
    Setting up libhtml-tagset-perl (3.20-6) ...
    Setting up liblwp-mediatypes-perl (6.04-2) ...
    Setting up libfcgi-bin (2.4.2-2.1ubuntu0.24.04.1) ...
    Setting up libencode-locale-perl (1.05-3) ...
    Setting up libsnappy1v5:amd64 (1.1.10-1build1) ...
    Setting up socat (1.8.0.0-4build3) ...
    Setting up libio-html-perl (1.004-3) ...
    Setting up libmariadb3:amd64 (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up libtimedate-perl (2.3300-2) ...
    Setting up pv (1.8.5-2build1) ...
    Setting up libfcgi-perl (0.82+ds-3build2) ...
    Setting up liburing2:amd64 (2.5-1build1) ...
    Setting up liburi-perl (5.27-1) ...
    Setting up libdbi-perl:amd64 (1.643-4build3) ...
    Setting up libhttp-date-perl (6.06-1) ...
    Setting up mariadb-client-core (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up libdbd-mysql-perl:amd64 (4.052-1ubuntu3) ...
    Setting up libhtml-parser-perl:amd64 (3.81-1build3) ...
    Setting up mariadb-server-core (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up libhttp-message-perl (6.45-1ubuntu1) ...
    Setting up mariadb-client (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up libcgi-pm-perl (4.63-1) ...
    Setting up libhtml-template-perl (2.97-2) ...
    Setting up mariadb-server (1:10.11.13-0ubuntu0.24.04.1) ...
    Created symlink /etc/systemd/system/multi-user.target.wants/mariadb.service → /usr/lib/systemd/system/mariadb.service.
    Setting up mariadb-plugin-provider-bzip2 (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up mariadb-plugin-provider-lzma (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up mariadb-plugin-provider-lzo (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up mariadb-plugin-provider-lz4 (1:10.11.13-0ubuntu0.24.04.1) ...
    Setting up libcgi-fast-perl (1:2.17-1) ...
    Setting up mariadb-plugin-provider-snappy (1:10.11.13-0ubuntu0.24.04.1) ...
    Processing triggers for man-db (2.12.0-4build2) ...
    Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
    Processing triggers for mariadb-server (1:10.11.13-0ubuntu0.24.04.1) ...
  
    Running kernel seems to be up-to-date.
  
    No services need to be restarted.
  
    No containers need to be restarted.
  
    No user sessions are running outdated binaries.
  
    No VM guests are running outdated hypervisor (qemu) binaries on this host.
  stdout_lines: <omitted>

TASK [fact_push : Create the facts directory in case it isn't there] **********************************************************************************************************************
changed: [controlplane] => changed=true 
  gid: 0
  group: root
  mode: '0755'
  owner: root
  path: /etc/ansible/facts.d
  size: 4096
  state: directory
  uid: 0
changed: [node01] => changed=true 
  gid: 0
  group: root
  mode: '0755'
  owner: root
  path: /etc/ansible/facts.d
  size: 4096
  state: directory
  uid: 0

TASK [fact_push : Push over the db_patching.fact] *****************************************************************************************************************************************
skipping: [controlplane] => changed=false 
  false_condition: '"db" in app'
  skip_reason: Conditional result was False
changed: [node01] => changed=true 
  checksum: 925e5a53291810ced7689f4b0ffa6661c3f269b0
  dest: /etc/ansible/facts.d/patching.fact
  gid: 0
  group: root
  md5sum: 5726b801f8102d19cf2401c8e776a831
  mode: '0644'
  owner: root
  size: 132
  src: /root/.ansible/tmp/ansible-tmp-1750101781.8766723-28787-5383940307214/source
  state: file
  uid: 0

TASK [fact_push : Push over the web_patching.fact] ****************************************************************************************************************************************
skipping: [node01] => changed=false 
  false_condition: '"web" in app'
  skip_reason: Conditional result was False
changed: [controlplane] => changed=true 
  checksum: 5eb4d4883c9c64cdc5b2325da4760281d64618c4
  dest: /etc/ansible/facts.d/patching.fact
  gid: 0
  group: root
  md5sum: b73ef6b9d9db89eaa0adc73aedcab2ee
  mode: '0644'
  owner: root
  size: 131
  src: /root/.ansible/tmp/ansible-tmp-1750101783.1635325-28823-23891451879123/source
  state: file
  uid: 0

TASK [packages_update : Upgrade all packages to the latest version] ***********************************************************************************************************************
skipping: [controlplane] => changed=false 
  false_condition: action == "update"
  skip_reason: Conditional result was False
skipping: [node01] => changed=false 
  false_condition: action == "update"
  skip_reason: Conditional result was False

PLAY RECAP ********************************************************************************************************************************************************************************
controlplane               : ok=5    changed=3    unreachable=0    failed=0    skipped=3    rescued=0    ignored=0   
node01                     : ok=5    changed=3    unreachable=0    failed=0    skipped=3    rescued=0    ignored=0
```
```bash
controlplane:~/HPC_Deploy$ ls -l /etc/ansible/facts.d/patching.fact 
-rw-r--r-- 1 root root 131 Jun 16 19:23 /etc/ansible/facts.d/patching.fact
node01:~$ ls -l /etc/ansible/facts.d/patching.fact 
-rw-r--r-- 1 root root 132 Jun 16 19:23 /etc/ansible/facts.d/patching.fact
```

What roles are being executed?
```bash
roles:
  - precheck
  - fact_push
  - patch
  - { role: reboot, when: ansible_local.patching.rebooting == "true" }
  - server_validation
  - app_validation
  - { role: report, when: report | default(false) == "true" }
  - ```
```bash
ansible-playbook -v -i /root/HPC_Deploy/hosts /root/HPC_Deploy/04_enterprise_patching.yaml
No config file found; using defaults

PLAY [all] ********************************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [controlplane]
ok: [node01]

TASK [precheck : Major Distribution] ******************************************************************************************************************************************************
changed: [controlplane] => {"add_group": "Ubuntu24", "changed": true, "parent_groups": ["all"]}
changed: [node01] => {"add_group": "Ubuntu24", "changed": true, "parent_groups": ["all"]}

TASK [precheck : Checking Rebooting flag] *************************************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "\"true\" in ansible_local.patching.rebooting", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "\"true\" in ansible_local.patching.rebooting", "skip_reason": "Conditional result was False"}

TASK [fact_push : Create the facts directory in case it isn't there] **********************************************************************************************************************
ok: [controlplane] => {"changed": false, "gid": 0, "group": "root", "mode": "0755", "owner": "root", "path": "/etc/ansible/facts.d", "size": 4096, "state": "directory", "uid": 0}
ok: [node01] => {"changed": false, "gid": 0, "group": "root", "mode": "0755", "owner": "root", "path": "/etc/ansible/facts.d", "size": 4096, "state": "directory", "uid": 0}

TASK [fact_push : Push over the db_patching.fact] *****************************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "\"db\" in app", "skip_reason": "Conditional result was False"}
ok: [node01] => {"changed": false, "checksum": "925e5a53291810ced7689f4b0ffa6661c3f269b0", "dest": "/etc/ansible/facts.d/patching.fact", "gid": 0, "group": "root", "mode": "0644", "owner": "root", "path": "/etc/ansible/facts.d/patching.fact", "size": 132, "state": "file", "uid": 0}

TASK [fact_push : Push over the web_patching.fact] ****************************************************************************************************************************************
skipping: [node01] => {"changed": false, "false_condition": "\"web\" in app", "skip_reason": "Conditional result was False"}
ok: [controlplane] => {"changed": false, "checksum": "5eb4d4883c9c64cdc5b2325da4760281d64618c4", "dest": "/etc/ansible/facts.d/patching.fact", "gid": 0, "group": "root", "mode": "0644", "owner": "root", "path": "/etc/ansible/facts.d/patching.fact", "size": 131, "state": "file", "uid": 0}

TASK [patch : Upgrade all packages to the latest version] *********************************************************************************************************************************
ok: [controlplane] => {"changed": false, "msg": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nCalculating upgrade...\n0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.\n", "stderr": "", "stderr_lines": [], "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nCalculating upgrade...\n0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.\n", "stdout_lines": ["Reading package lists...", "Building dependency tree...", "Reading state information...", "Calculating upgrade...", "0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded."]}
ok: [node01] => {"changed": false, "msg": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nCalculating upgrade...\nThe following package was automatically installed and is no longer required:\n  squashfs-tools\nUse 'apt autoremove' to remove it.\n0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.\n", "stderr": "", "stderr_lines": [], "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nCalculating upgrade...\nThe following package was automatically installed and is no longer required:\n  squashfs-tools\nUse 'apt autoremove' to remove it.\n0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.\n", "stdout_lines": ["Reading package lists...", "Building dependency tree...", "Reading state information...", "Calculating upgrade...", "The following package was automatically installed and is no longer required:", "  squashfs-tools", "Use 'apt autoremove' to remove it.", "0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded."]}

TASK [patch : install need-restart] *******************************************************************************************************************************************************
ok: [controlplane] => {"cache_update_time": 1750099275, "cache_updated": false, "changed": false}
ok: [node01] => {"cache_update_time": 1750099295, "cache_updated": false, "changed": false}

TASK [patch : Upgrade all packages to the latest version on Rocky or RHEL] ****************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_distribution == \"Rocky\" or ansible_distribution == \"RHEL\"", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "ansible_distribution == \"Rocky\" or ansible_distribution == \"RHEL\"", "skip_reason": "Conditional result was False"}

TASK [patch : install needsrestart] *******************************************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_distribution == \"Rocky\" or ansible_distribution == \"RHEL\"", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "ansible_distribution == \"Rocky\" or ansible_distribution == \"RHEL\"", "skip_reason": "Conditional result was False"}

TASK [reboot : Check for reboot requirement] **********************************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}

TASK [reboot : Check for reboot requirement on Rocky or RHEL] *****************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}

TASK [reboot : Set reboot_required fact] **************************************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}

TASK [reboot : Reboot if needed] **********************************************************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}
skipping: [node01] => {"changed": false, "false_condition": "ansible_local.patching.rebooting == \"true\"", "skip_reason": "Conditional result was False"}

TASK [server_validation : Check server uptime] ********************************************************************************************************************************************
ok: [controlplane] => {"changed": false, "cmd": ["uptime"], "delta": "0:00:00.005499", "end": "2025-06-16 19:33:54.357767", "msg": "", "rc": 0, "start": "2025-06-16 19:33:54.352268", "stderr": "", "stderr_lines": [], "stdout": " 19:33:54 up 53 min,  1 user,  load average: 4.85, 3.04, 1.46", "stdout_lines": [" 19:33:54 up 53 min,  1 user,  load average: 4.85, 3.04, 1.46"]}
ok: [node01] => {"changed": false, "cmd": ["uptime"], "delta": "0:00:00.007739", "end": "2025-06-16 19:33:54.400602", "msg": "", "rc": 0, "start": "2025-06-16 19:33:54.392863", "stderr": "", "stderr_lines": [], "stdout": " 19:33:54 up 53 min,  0 user,  load average: 1.06, 0.90, 0.40", "stdout_lines": [" 19:33:54 up 53 min,  0 user,  load average: 1.06, 0.90, 0.40"]}

TASK [app_validation : Check apache if web server is running] *****************************************************************************************************************************
skipping: [node01] => {"changed": false, "false_condition": "ansible_local.patching.webserver == 'true'", "skip_reason": "Conditional result was False"}
ok: [controlplane] => {"changed": false, "cmd": "ps -ef | grep [a]pache", "delta": "0:00:00.021390", "end": "2025-06-16 19:33:54.885659", "msg": "", "rc": 0, "start": "2025-06-16 19:33:54.864269", "stderr": "", "stderr_lines": [], "stdout": "www-data   50667       1  0 19:33 ?        00:00:00 /usr/bin/htcacheclean -d 120 -p /var/cache/apache2/mod_cache_disk -l 300M -n\nroot       50771       1  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start\nwww-data   50807   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start\nwww-data   50808   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start\nwww-data   50809   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start\nwww-data   50810   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start\nwww-data   50816   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start", "stdout_lines": ["www-data   50667       1  0 19:33 ?        00:00:00 /usr/bin/htcacheclean -d 120 -p /var/cache/apache2/mod_cache_disk -l 300M -n", "root       50771       1  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start", "www-data   50807   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start", "www-data   50808   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start", "www-data   50809   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start", "www-data   50810   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start", "www-data   50816   50771  0 19:33 ?        00:00:00 /usr/sbin/apache2 -k start"]}

TASK [app_validation : check database if database server is running] **********************************************************************************************************************
skipping: [controlplane] => {"changed": false, "false_condition": "ansible_local.patching.database == 'true'", "skip_reason": "Conditional result was False"}
ok: [node01] => {"changed": false, "cmd": "ps -ef | grep [m]ysql", "delta": "0:00:00.022806", "end": "2025-06-16 19:33:55.457067", "msg": "", "rc": 0, "start": "2025-06-16 19:33:55.434261", "stderr": "", "stderr_lines": [], "stdout": "mysql      34654       1  0 19:33 ?        00:00:00 /usr/sbin/mariadbd", "stdout_lines": ["mysql      34654       1  0 19:33 ?        00:00:00 /usr/sbin/mariadbd"]}

PLAY RECAP ********************************************************************************************************************************************************************************
controlplane               : ok=8    changed=1    unreachable=0    failed=0    skipped=9    rescued=0    ignored=0   
node01                     : ok=8    changed=1    unreachable=0    failed=0    skipped=9    rescued=0    ignored=0
```
