```bash
sysctl -a | grep -i ipv4 | grep -i forward
```
```bash
net.ipv4.conf.all.bc_forwarding = 0
net.ipv4.conf.all.forwarding = 0
net.ipv4.conf.all.mc_forwarding = 0
net.ipv4.conf.default.bc_forwarding = 0
net.ipv4.conf.default.forwarding = 0
net.ipv4.conf.default.mc_forwarding = 0
net.ipv4.conf.eth0.bc_forwarding = 0
net.ipv4.conf.eth0.forwarding = 0
net.ipv4.conf.eth0.mc_forwarding = 0
net.ipv4.conf.lo.bc_forwarding = 0
net.ipv4.conf.lo.forwarding = 0
net.ipv4.conf.lo.mc_forwarding = 0
net.ipv4.ip_forward = 0
net.ipv4.ip_forward_update_priority = 1
net.ipv4.ip_forward_use_pmtu = 0
```

Does this system appear to be set to forward? Why or why not?

```bash
sysctl -a | grep -i ipv4 | grep -i martian
```
```bash
net.ipv4.conf.all.log_martians = 0
net.ipv4.conf.default.log_martians = 0
net.ipv4.conf.eth0.log_martians = 0
net.ipv4.conf.lo.log_martians = 0
```

What are martians and is this system allowing them?

```bash
sysctl -a | grep -i panic
```
```bash
kernel.hardlockup_panic = 1
kernel.hung_task_panic = 0
kernel.max_rcu_stall_to_panic = 0
kernel.panic = 0
kernel.panic_on_io_nmi = 0
kernel.panic_on_oops = 1
kernel.panic_on_rcu_stall = 0
kernel.panic_on_unrecovered_nmi = 0
kernel.panic_on_warn = 0
kernel.panic_print = 0
kernel.softlockup_panic = 0
kernel.unknown_nmi_panic = 0
vm.panic_on_oom = 0
```

How does this system handle panics?

```bash
sysctl -a | grep -i crypto
```
```bash
crypto.fips_enabled = 0
crypto.fips_name = Rocky Linux 9 - Kernel Cryptographic API
crypto.fips_version = 5.14.0-427.18.1.el9_4.x86_64
```

What are the settings you see? Is FIPS enabled?

```bash
cat /proc/cmdline
```
```bash
initrd=initramfs  rd.neednet=1 root=wwinit wwinit.container=http://192.168.200.25:9873/provision/0e:84:26:36:b7:c8?assetkey=&uuid=d7e506b1-27cd-8da9-0174-c056606c9ec5&stage=container&compress=gz wwinit.system=http://192.168.200.25:9873/provision/0e:84:26:36:b7:c8?assetkey=&uuid=d7e506b1-27cd-8da9-0174-c056606c9ec5&stage=system&compress=gz wwinit.runtime=http://192.168.200.25:9873/provision/0e:84:26:36:b7:c8?assetkey=&uuid=d7e506b1-27cd-8da9-0174-c056606c9ec5&stage=runtime&compress=gz init=/init wwid=0e:84:26:36:b7:c8 quiet crashkernel=no vga=791 net.naming-scheme=v238
```
```bash
fips-mode-setup --check
```
```bash
Installation of FIPS modules is not completed.
FIPS mode is disabled.
```
```bash
sestatus
```
```bash
SELinux status:                 enabled
SELinuxfs mount:                /sys/fs/selinux
SELinux root directory:         /etc/selinux
Loaded policy name:             targeted
Current mode:                   permissive
Mode from config file:          permissive
Policy MLS status:              enabled
Policy deny_unknown status:     allowed
Memory protection checking:     actual (secure)
Max kernel policy version:      33
```
```bash
cat /etc/selinux/config
```
```bash
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=permissive
# SELINUXTYPE= can take one of three two values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```

What information about the security posture of the system can you see here?  
Can you verify SELINUX status?  
Can you verify FIPS status?

#### [Examine STIG V-257957](https://professionallinuxusersgroup.github.io/psc/u2lab.html#examine-stig-v-257957)

What is the problem?  
	RHEL 9 must be configured to use TCP syncookie
What is the fix?  
	Configure RHEL 9 to use TCP syncookies.
What type of control is being implemented?  
Is it set properly on your system?

```bash
sysctl -a | grep -i ipv4 | grep -i syncookies
```
```bash
net.ipv4.tcp_syncookies = 1
```

#### [Check and remediate V-257958 STIG](https://professionallinuxusersgroup.github.io/psc/u2lab.html#check-and-remediate-v-257958-stig)

What is the problem?  
	RHEL 9 must ignore Internet Protocol version 4 (IPv4) Internet Control Message Protocol (ICMP) redirect messages.
What is the fix?  
	Configure RHEL 9 to ignore IPv4 ICMP redirect messages.
What type of control is being implemented?  
Is it set properly on your system?

```bash
sysctl net.ipv4.conf.all.accept_redirects
```
```bash
net.ipv4.conf.all.accept_redirects = 0
```

V-257960 & V-257961
What is the problem? How are they related?
	RHEL 9 must log IPv4 packets with impossible addresses.
	RHEL 9 must log IPv4 packets with impossible addresses by default.
What is the fix?  
	Configure RHEL 9 to log martian packets on IPv4 interfaces.
	Configure RHEL 9 to log martian packets on IPv4 interfaces by default.
What type of control is being implemented?  
Is it set properly on your system?
```bash
sysctl net.ipv4.conf.all.log_martians
```
```bash
net.ipv4.conf.all.log_martians = 0
```
```bash
sysctl net.ipv4.conf.default.log_martians
```
```bash
net.ipv4.conf.default.log_martians = 0
```
```bash
vi /etc/sysctl.d/98-remediate.conf
```
```
net.ipv4.conf.default.log_martians=1
net.ipv4.conf.all.log_martians=1
```

#### [Filter by firewall](https://professionallinuxusersgroup.github.io/psc/u2lab.html#filter-by-firewall)

How many STIGS do you see? 7
What do these STIGS appear to be trying to do? What types of controls are they?

```bash
# Verify that your firewall is running
systemctl status firewalld

● firewalld.service - firewalld - dynamic firewall daemon
     Loaded: loaded (/usr/lib/systemd/system/firewalld.service; enabled; preset: enabled)
     Active: active (running) since Sat 2025-06-07 09:41:50 MST; 1 week 0 days ago
       Docs: man:firewalld(1)
   Main PID: 742 (firewalld)
      Tasks: 2 (limit: 24363)
     Memory: 24.4M
        CPU: 587ms
     CGroup: /system.slice/firewalld.service
             └─742 /usr/bin/python3 -s /usr/sbin/firewalld --nofork --nopid

Jun 07 09:41:50 hammer9 systemd[1]: Starting firewalld - dynamic firewall daemon...
Jun 07 09:41:50 hammer9 systemd[1]: Started firewalld - dynamic firewall daemon.


# Verify that your firewall has the service defined
firewall-cmd --get-services | grep -i node

RH-Satellite-6 RH-Satellite-6-capsule afp amanda-client amanda-k5-client amqp amqps apcupsd audit ausweisapp2 bacula bacula-client bareos-director bareos-filedaemon bareos-storage bb bgp bitcoin bitcoin-rpc bitcoin-testnet bitcoin-testnet-rpc bittorrent-lsd ceph ceph-exporter ceph-mon cfengine checkmk-agent cockpit collectd condor-collector cratedb ctdb dds dds-multicast dds-unicast dhcp dhcpv6 dhcpv6-client distcc dns dns-over-tls docker-registry docker-swarm dropbox-lansync elasticsearch etcd-client etcd-server finger foreman foreman-proxy freeipa-4 freeipa-ldap freeipa-ldaps freeipa-replication freeipa-trust ftp galera ganglia-client ganglia-master git gpsd grafana gre high-availability http http3 https ident imap imaps ipfs ipp ipp-client ipsec irc ircs iscsi-target isns jenkins kadmin kdeconnect kerberos kibana klogin kpasswd kprop kshell kube-api kube-apiserver kube-control-plane kube-control-plane-secure kube-controller-manager kube-controller-manager-secure kube-nodeport-services kube-scheduler kube-scheduler-secure kube-worker kubelet kubelet-readonly kubelet-worker ldap ldaps libvirt libvirt-tls lightning-network llmnr llmnr-client llmnr-tcp llmnr-udp managesieve matrix mdns memcache minidlna mongodb mosh mountd mqtt mqtt-tls ms-wbt mssql murmur mysql nbd nebula netbios-ns netdata-dashboard nfs nfs3 nmea-0183 nrpe ntp nut openvpn ovirt-imageio ovirt-storageconsole ovirt-vmconsole plex pmcd pmproxy pmwebapi pmwebapis pop3 pop3s postgresql privoxy prometheus prometheus-node-exporter proxy-dhcp ps2link ps3netsrv ptp pulseaudio puppetmaster quassel radius rdp redis redis-sentinel rpc-bind rquotad rsh rsyncd rtsp salt-master samba samba-client samba-dc sane sip sips slp smtp smtp-submission smtps snmp snmptls snmptls-trap snmptrap spideroak-lansync spotify-sync squid ssdp ssh steam-streaming svdrp svn syncthing syncthing-gui syncthing-relay synergy syslog syslog-tls telnet tentacle tftp tile38 tinc tor-socks transmission-client upnp-client vdsm vnc-server warpinator wbem-http wbem-https wireguard ws-discovery ws-discovery-client ws-discovery-tcp ws-discovery-udp wsman wsmans xdmcp xmpp-bosh xmpp-client xmpp-local xmpp-server zabbix-agent zabbix-server zerotier

ls /usr/lib/firewalld/services | grep -i node
kube-nodeport-services.xml
prometheus-node-exporter.xml

# Verify that the service is not currently enabled for node_exporter
firewall-cmd --list-services

cockpit dhcpv6-client ssh

# Examine the structure of the firewall .xml file
cat /usr/lib/firewalld/services/prometheus-node-exporter.xml

<?xml version="1.0" encoding="utf-8"?>
<service>
  <short>prometheus-node-exporter</short>
  <description>The node-exporter agent for Prometheus monitoring system.</description>
  <port protocol="tcp" port="9100"/>
</service>


# Enable the service through your firewall
firewall-cmd --permanent --add-service=prometheus-node-exporter
success

# Reload so the changes take effect
firewall-cmd --reload
success

# Verify that the service is currently enabled for node_exporter
firewall-cmd --list-services
cockpit dhcpv6-client prometheus-node-exporter ssh

```

```bash
cd /root
mkdir stigs
cd stigs
wget -O U_RHEL_9_V2R4_STIG_Ansible.zip https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_RHEL_9_V2R4_STIG_Ansible.zip
unzip U_RHEL_9_V2R4_STIG_Ansible.zip
mkdir ansible
cp rhel9STIG-ansible.zip ansible/
cd ansible
unzip rhel9STIG-ansible.zip
```
```bash
--2025-06-14 15:12:23--  https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_RHEL_9_V2R4_STIG_Ansible.zip
Resolving dl.dod.cyber.mil (dl.dod.cyber.mil)... 18.238.96.66, 18.238.96.67, 18.238.96.76, ...
Connecting to dl.dod.cyber.mil (dl.dod.cyber.mil)|18.238.96.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 626271 (612K) [application/zip]
Saving to: ‘U_RHEL_9_V2R4_STIG_Ansible.zip’

U_RHEL_9_V2R4_STIG_Ansible.zip                      100%[=================================================================================================================>] 611.59K  --.-KB/s    in 0.07s

2025-06-14 15:12:24 (8.13 MB/s) - ‘U_RHEL_9_V2R4_STIG_Ansible.zip’ saved [626271/626271]

Archive:  U_RHEL_9_V2R4_STIG_Ansible.zip
  inflating: rhel9STIG-ansible.zip
  inflating: U_RHEL_9_V2R4_STIG_Ansible_Documentation.pdf
Archive:  rhel9STIG-ansible.zip
   creating: roles/
   creating: roles/rhel9STIG/
   creating: roles/rhel9STIG/callback_plugins/
   creating: roles/rhel9STIG/files/
   creating: roles/rhel9STIG/defaults/
   creating: roles/rhel9STIG/handlers/
   creating: roles/rhel9STIG/tasks/
 extracting: enforce.sh
 extracting: site.yml
 extracting: ansible.cfg
 extracting: roles/rhel9STIG/callback_plugins/stig_xml.py
 extracting: roles/rhel9STIG/files/U_RHEL_9_STIG_V2R4_Manual-xccdf.xml
 extracting: roles/rhel9STIG/handlers/main.yml
 extracting: roles/rhel9STIG/defaults/main.yml
 extracting: roles/rhel9STIG/tasks/main.yml
```

```bash
cd /root/stigs/ansible/roles/rhel9STIG/defaults/
vim main.yml
```
```bash
vim /root/stigs/ansible/roles/rhel9STIG/tasks/main.yml
```
```yaml
# R-257784 RHEL-09-211045
- name: stigrule_257784__etc_systemd_system_conf
  ini_file:
    path: /etc/systemd/system.conf
    section: Manager
    option: CtrlAltDelBurstAction
    value: "{{ rhel9STIG_stigrule_257784__etc_systemd_system_conf_Value }}"
    no_extra_spaces: yes
  notify: daemon_reload
  when:
    - rhel9STIG_stigrule_257784_Manage
```

```bash
dnf -y install openscap-scanner openscap-utils openscap-scanner scap-security-guide
cd /root
mkdir openscap
cd openscap

# Generate the Ansible
oscap xccdf generate fix --profile ospp --fix-type ansible /usr/share/xml/scap/ssg/content/ssg-rhel9-ds.xml > draft-disa-remediate.yml

# Examine the file
vim draft-disa-remediate.yml

# Generate a BASH version
oscap xccdf generate fix --profile ospp --fix-type bash /usr/share/xml/scap/ssg/content/ssg-rhel9-ds.xml > draft-disa-remediate.sh

# Examine the file
vim draf-disa-remediate.sh
```


