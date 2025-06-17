
- Check your stig viewer and go to RHEL 9 stigs.
    
- Set a filter for “change management”.
    
    - How many STIGs do you see?

![[Pasted image 20250614131053.png]]
- Review the wording, what is meant by a robust change management process?
    
    - Do you think this can be applied in just one STIG? Why or why not?
    - What type of control is being implemented with change management in these STIGS?
        - Is it different across the STIGs or all the same?



*apt -y install aide
```bash
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following package was automatically installed and is no longer required:
  squashfs-tools
Use 'apt autoremove' to remove it.
The following additional packages will be installed:
  aide-common bsd-mailx liblockfile-bin liblockfile1 libmhash2 libnsl2 postfix ssl-cert
Suggested packages:
  figlet postfix-cdb postfix-doc postfix-ldap postfix-lmdb postfix-mta-sts-resolver postfix-mysql postfix-pcre postfix-pgsql postfix-sqlite procmail sasl2-bin | dovecot-common
The following NEW packages will be installed:
  aide aide-common bsd-mailx liblockfile-bin liblockfile1 libmhash2 libnsl2 postfix ssl-cert
0 upgraded, 9 newly installed, 0 to remove and 162 not upgraded.
Need to get 1692 kB of archives.
After this operation, 5570 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble/main amd64 ssl-cert all 1.1.2ubuntu1 [17.8 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 libnsl2 amd64 1.3.0-3build3 [41.4 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble/main amd64 postfix amd64 3.8.6-1build2 [1254 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble/main amd64 libmhash2 amd64 0.9.9.9-9build3 [94.2 kB]
Get:5 http://archive.ubuntu.com/ubuntu noble/main amd64 aide amd64 0.18.6-2build2 [117 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble/main amd64 liblockfile-bin amd64 1.17-1build3 [11.2 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble/main amd64 liblockfile1 amd64 1.17-1build3 [6840 B]
Get:8 http://archive.ubuntu.com/ubuntu noble/main amd64 aide-common all 0.18.6-2build2 [82.2 kB]
Get:9 http://archive.ubuntu.com/ubuntu noble/main amd64 bsd-mailx amd64 8.1.2-0.20220412cvs-1build1 [67.2 kB]
Fetched 1692 kB in 1s (1957 kB/s)    
Preconfiguring packages ...
Selecting previously unselected package ssl-cert.
(Reading database ... 82155 files and directories currently installed.)
Preparing to unpack .../0-ssl-cert_1.1.2ubuntu1_all.deb ...
Unpacking ssl-cert (1.1.2ubuntu1) ...
Selecting previously unselected package libnsl2:amd64.
Preparing to unpack .../1-libnsl2_1.3.0-3build3_amd64.deb ...
Unpacking libnsl2:amd64 (1.3.0-3build3) ...
Selecting previously unselected package postfix.
Preparing to unpack .../2-postfix_3.8.6-1build2_amd64.deb ...
Unpacking postfix (3.8.6-1build2) ...
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack .../3-libmhash2_0.9.9.9-9build3_amd64.deb ...
Unpacking libmhash2:amd64 (0.9.9.9-9build3) ...
Selecting previously unselected package aide.
Preparing to unpack .../4-aide_0.18.6-2build2_amd64.deb ...
Unpacking aide (0.18.6-2build2) ...
Selecting previously unselected package liblockfile-bin.
Preparing to unpack .../5-liblockfile-bin_1.17-1build3_amd64.deb ...
Unpacking liblockfile-bin (1.17-1build3) ...
Selecting previously unselected package liblockfile1:amd64.
Preparing to unpack .../6-liblockfile1_1.17-1build3_amd64.deb ...
Unpacking liblockfile1:amd64 (1.17-1build3) ...
Selecting previously unselected package aide-common.
Preparing to unpack .../7-aide-common_0.18.6-2build2_all.deb ...
Unpacking aide-common (0.18.6-2build2) ...
Selecting previously unselected package bsd-mailx.
Preparing to unpack .../8-bsd-mailx_8.1.2-0.20220412cvs-1build1_amd64.deb ...
Unpacking bsd-mailx (8.1.2-0.20220412cvs-1build1) ...
Setting up liblockfile-bin (1.17-1build3) ...
Setting up ssl-cert (1.1.2ubuntu1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/ssl-cert.service → /usr/lib/systemd/system/ssl-cert.service.
Setting up libmhash2:amd64 (0.9.9.9-9build3) ...
Setting up libnsl2:amd64 (1.3.0-3build3) ...
Setting up liblockfile1:amd64 (1.17-1build3) ...
Setting up aide (0.18.6-2build2) ...
Setting up postfix (3.8.6-1build2) ...
info: Selecting GID from range 100 to 999 ...
info: Adding group `postfix' (GID 114) ...
info: Selecting UID from range 100 to 999 ...

info: Adding system user `postfix' (UID 109) ...
info: Adding new user `postfix' (UID 109) with group `postfix' ...
info: Not creating home directory `/var/spool/postfix'.
Creating /etc/postfix/dynamicmaps.cf
info: Selecting GID from range 100 to 999 ...
info: Adding group `postdrop' (GID 115) ...
/etc/aliases does not exist, creating it.

Postfix (main.cf) was not set up.  Start with
  cp /usr/share/postfix/main.cf.debian /etc/postfix/main.cf
.  If you need to make changes, edit /etc/postfix/main.cf (and others) as 
needed.  To view Postfix configuration values, see postconf(1).

After modifying main.cf, be sure to run 'systemctl reload postfix'.

Created symlink /etc/systemd/system/multi-user.target.wants/postfix.service → /usr/lib/systemd/system/postfix.service.
Setting up aide-common (0.18.6-2build2) ...
Creating config file /etc/aide/aide.settings.d/31_aide_torrus_settings with new version
Creating config file /etc/aide/aide.settings.d/31_aide_svn-server_settings with new version
Creating config file /etc/aide/aide.settings.d/31_aide_trac_settings with new version
Creating config file /etc/aide/aide.settings.d/31_aide_apt_settings with new version
Creating config file /etc/aide/aide.settings.d/10_aide_sourceslist with new version
Creating config file /etc/aide/aide.conf.d/31_aide_tmux with new version
Creating config file /etc/aide/aide.conf.d/31_aide_fail2ban with new version
Creating config file /etc/aide/aide.conf.d/31_aide_mail with new version
Creating config file /etc/aide/aide.conf.d/31_aide_asterisk with new version
Creating config file /etc/aide/aide.conf.d/31_aide_etckeeper with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-timesyncd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_smokeping with new version
Creating config file /etc/aide/aide.conf.d/31_aide_e2fsprogs with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-machined with new version
Creating config file /etc/aide/aide.conf.d/31_aide_fake-hwclock with new version
Creating config file /etc/aide/aide.conf.d/31_aide_borgbackup with new version
Creating config file /etc/aide/aide.conf.d/31_aide_openvpn-server with new version
Creating config file /etc/aide/aide.conf.d/31_aide_cups with new version
Creating config file /etc/aide/aide.conf.d/31_aide_slapd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_adjtime with new version
Creating config file /etc/aide/aide.conf.d/31_aide_network with new version
Creating config file /etc/aide/aide.conf.d/10_aide_machineid with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apt with new version
Creating config file /etc/aide/aide.conf.d/31_aide_icinga2 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_tt-rss with new version
Creating config file /etc/aide/aide.conf.d/31_aide_haveged with new version
Creating config file /etc/aide/aide.conf.d/31_aide_spamassassin with new version
Creating config file /etc/aide/aide.conf.d/31_aide_torrus with new version
Creating config file /etc/aide/aide.conf.d/31_aide_trac with new version
Creating config file /etc/aide/aide.conf.d/31_aide_wtmp with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-cron with new version
Creating config file /etc/aide/aide.conf.d/31_aide_x11-xkb-utils with new version
Creating config file /etc/aide/aide.conf.d/31_aide_exim4_exiscan with new version
Creating config file /etc/aide/aide.conf.d/31_aide_tlp with new version
Creating config file /etc/aide/aide.conf.d/30_inn2_vars with new version
Creating config file /etc/aide/aide.conf.d/31_aide_mdadm with new version
Creating config file /etc/aide/aide.conf.d/31_aide_udev with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ippl with new version
Creating config file /etc/aide/aide.conf.d/31_aide_man with new version
Creating config file /etc/aide/aide.conf.d/31_aide_greylistd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_xe-guest-utilities with new version
Creating config file /etc/aide/aide.conf.d/31_aide_rsnapshot with new version
Creating config file /etc/aide/aide.conf.d/31_aide_inn2 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_aptitude with new version
Creating config file /etc/aide/aide.conf.d/70_aide_proc_sys with new version
Creating config file /etc/aide/aide.conf.d/31_aide_pm-utils with new version
Creating config file /etc/aide/aide.conf.d/31_aide_initscripts with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dmeventd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_postgrey with new version
Creating config file /etc/aide/aide.conf.d/31_aide_libvirt with new version
Creating config file /etc/aide/aide.conf.d/31_aide_opie-server with new version
Creating config file /etc/aide/aide.conf.d/31_aide_samba with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apache2-fcgid with new version
Creating config file /etc/aide/aide.conf.d/31_aide_php-common with new version
Creating config file /etc/aide/aide.conf.d/31_aide_bind9 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_fcron with new version
Creating config file /etc/aide/aide.conf.d/31_aide_exim4 with new version
Creating config file /etc/aide/aide.conf.d/70_aide_tmp with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apt-listbugs with new version
Creating config file /etc/aide/aide.conf.d/31_aide_run_systemd_resolve with new version
Creating config file /etc/aide/aide.conf.d/31_aide_munin-nodes with new version
Creating config file /etc/aide/aide.conf.d/31_aide_nslcd with new version
Creating config file /etc/aide/aide.conf.d/10_aide_constants with new version
Creating config file /etc/aide/aide.conf.d/20_aide_run_systemd-journald with new version
Creating config file /etc/aide/aide.conf.d/31_aide_haproxy with new version
Creating config file /etc/aide/aide.conf.d/31_aide_syslog-ng with new version
Creating config file /etc/aide/aide.conf.d/31_aide_laptop-mode-tools with new version
Creating config file /etc/aide/aide.conf.d/31_aide_snmpd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_vsftpd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_run_tmpfiles with new version
Creating config file /etc/aide/aide.conf.d/31_aide_rngd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_cron with new version
Creating config file /etc/aide/aide.conf.d/31_aide_cron-apt with new version
Creating config file /etc/aide/aide.conf.d/31_aide_at with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-journald with new version
Creating config file /etc/aide/aide.conf.d/31_aide_munin-node with new version
Creating config file /etc/aide/aide.conf.d/31_aide_pam_motd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_debspawn with new version
Creating config file /etc/aide/aide.conf.d/31_aide_logrotate with new version
Creating config file /etc/aide/aide.conf.d/31_aide_runuser with new version
Creating config file /etc/aide/aide.conf.d/31_aide_network-manager with new version
Creating config file /etc/aide/aide.conf.d/10_aide_logext with new version
Creating config file /etc/aide/aide.conf.d/10_aide_hostname with new version
Creating config file /etc/aide/aide.conf.d/31_aide_amavisd-new with new version
Creating config file /etc/aide/aide.conf.d/31_aide_needrestart with new version
Creating config file /etc/aide/aide.conf.d/31_aide_anacron with new version
Creating config file /etc/aide/aide.conf.d/31_aide_cereal with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dovecot with new version
Creating config file /etc/aide/aide.conf.d/31_aide_postfix-cluebringer with new version
Creating config file /etc/aide/aide.conf.d/31_aide_amanda-server with new version
Creating config file /etc/aide/aide.conf.d/31_aide_console-setup with new version
Creating config file /etc/aide/aide.conf.d/31_aide_findutils with new version
Creating config file /etc/aide/aide.conf.d/10_aide_year with new version
Creating config file /etc/aide/aide.conf.d/31_aide_run_systemd_netif with new version
Creating config file /etc/aide/aide.conf.d/31_aide_locales with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dpkg with new version
Creating config file /etc/aide/aide.conf.d/31_aide_root-dotfiles with new version
Creating config file /etc/aide/aide.conf.d/31_aide_clamav-freshclam with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-networkd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_aide with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apt-show-versions with new version
Creating config file /etc/aide/aide.conf.d/31_aide_portmap with new version
Creating config file /etc/aide/aide.conf.d/31_aide_nscd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_saslauthd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_plocate with new version
Creating config file /etc/aide/aide.conf.d/21_aide_run_agetty with new version
Creating config file /etc/aide/aide.conf.d/31_aide_modules with new version
Creating config file /etc/aide/aide.conf.d/31_aide_xdm with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-nspawn with new version
Creating config file /etc/aide/aide.conf.d/31_aide_proftpd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_sudo with new version
Creating config file /etc/aide/aide.conf.d/31_aide_exim4_logs with new version
Creating config file /etc/aide/aide.conf.d/31_aide_oidentd with new version
Creating config file /etc/aide/aide.conf.d/30_aide_bind9 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_kerberos with new version
Creating config file /etc/aide/aide.conf.d/31_aide_atop with new version
Creating config file /etc/aide/aide.conf.d/10_aide_prevyear with new version
Creating config file /etc/aide/aide.conf.d/31_aide_mysql-server with new version
Creating config file /etc/aide/aide.conf.d/31_aide_privoxy with new version
Creating config file /etc/aide/aide.conf.d/31_aide_acpid with new version
Creating config file /etc/aide/aide.conf.d/10_aide_distribution with new version
Creating config file /etc/aide/aide.conf.d/31_aide_courier-authlib with new version
Creating config file /etc/aide/aide.conf.d/31_aide_console-log with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apt-listchanges with new version
Creating config file /etc/aide/aide.conf.d/31_aide_php7 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_munin with new version
Creating config file /etc/aide/aide.conf.d/31_aide_lvm2 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dev with new version
Creating config file /etc/aide/aide.conf.d/70_aide_dev with new version
Creating config file /etc/aide/aide.conf.d/31_aide_bandwidthd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd-resolved with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ifplugd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_inetd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_netdata with new version
Creating config file /etc/aide/aide.conf.d/31_aide_openvpn with new version
Creating config file /etc/aide/aide.conf.d/31_aide_lastlog with new version
Creating config file /etc/aide/aide.conf.d/31_aide_xinetd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dlocate with new version
Creating config file /etc/aide/aide.conf.d/31_aide_unbound with new version
Creating config file /etc/aide/aide.conf.d/31_aide_anubis with new version
Creating config file /etc/aide/aide.conf.d/31_aide_logcheck with new version
Creating config file /etc/aide/aide.conf.d/31_aide_svn-server with new version
Creating config file /etc/aide/aide.conf.d/31_aide_resolvconf with new version
Creating config file /etc/aide/aide.conf.d/31_aide_chrony with new version
Creating config file /etc/aide/aide.conf.d/31_aide_postgresql-15 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_lpd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dehydrated with new version
Creating config file /etc/aide/aide.conf.d/31_aide_initramfs-tools with new version
Creating config file /etc/aide/aide.conf.d/31_aide_debconf with new version
Creating config file /etc/aide/aide.conf.d/99_aide_root with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ssh-agent with new version
Creating config file /etc/aide/aide.conf.d/31_aide_pcscd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_avahi-daemon with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apache2 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_grub-efi with new version
Creating config file /etc/aide/aide.conf.d/31_aide_hald with new version
Creating config file /etc/aide/aide.conf.d/31_aide_checksecurity with new version
Creating config file /etc/aide/aide.conf.d/31_aide_smartmontools with new version
Creating config file /etc/aide/aide.conf.d/31_aide_webalizer with new version
Creating config file /etc/aide/aide.conf.d/31_aide_sniproxy with new version
Creating config file /etc/aide/aide.conf.d/31_aide_clamav with new version
Creating config file /etc/aide/aide.conf.d/31_aide_btmp with new version
Creating config file /etc/aide/aide.conf.d/31_aide_amanda-client with new version
Creating config file /etc/aide/aide.conf.d/31_aide_lldpd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dokuwiki with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apt-cacher-ng with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ddclient with new version
Creating config file /etc/aide/aide.conf.d/31_aide_nginx with new version
Creating config file /etc/aide/aide.conf.d/31_aide_isc-dhcp-client with new version
Creating config file /etc/aide/aide.conf.d/31_aide_schroot with new version
Creating config file /etc/aide/aide.conf.d/31_aide_gnupg with new version
Creating config file /etc/aide/aide.conf.d/31_aide_php-fpm with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dcc-common with new version
Creating config file /etc/aide/aide.conf.d/31_aide_dbus with new version
Creating config file /etc/aide/aide.conf.d/31_aide_irqbalance with new version
Creating config file /etc/aide/aide.conf.d/31_aide_screen with new version
Creating config file /etc/aide/aide.conf.d/31_aide_mariadb with new version
Creating config file /etc/aide/aide.conf.d/31_aide_nrpe with new version
Creating config file /etc/aide/aide.conf.d/31_aide_util-linux with new version
Creating config file /etc/aide/aide.conf.d/31_aide_clamav-unofficial-sigs with new version
Creating config file /etc/aide/aide.conf.d/10_aide_run with new version
Creating config file /etc/aide/aide.conf.d/31_aide_postfix with new version
Creating config file /etc/aide/aide.conf.d/31_aide_systemd_sessions with new version
Creating config file /etc/aide/aide.conf.d/31_aide_alsa with new version
Creating config file /etc/aide/aide.conf.d/31_aide_x11-common with new version
Creating config file /etc/aide/aide.conf.d/21_aide_spamassassin with new version
Creating config file /etc/aide/aide.conf.d/31_aide_utmp with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ntpsec with new version
Creating config file /etc/aide/aide.conf.d/31_aide_wpasupplicant with new version
Creating config file /etc/aide/aide.conf.d/31_aide_apcupsd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_tiger with new version
Creating config file /etc/aide/aide.conf.d/31_aide_slrn with new version
Creating config file /etc/aide/aide.conf.d/31_aide_rsyslog with new version
Creating config file /etc/aide/aide.conf.d/31_aide_spampd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_squid with new version
Creating config file /etc/aide/aide.conf.d/70_aide_etc with new version
Creating config file /etc/aide/aide.conf.d/31_aide_rkhunter with new version
Creating config file /etc/aide/aide.conf.d/70_aide_run with new version
Creating config file /etc/aide/aide.conf.d/31_aide_hapsd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_boinc-client with new version
Creating config file /etc/aide/aide.conf.d/31_aide_vpnc with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ufw with new version
Creating config file /etc/aide/aide.conf.d/31_aide_lighttpd with new version
Creating config file /etc/aide/aide.conf.d/31_aide_debsecan with new version
Creating config file /etc/aide/aide.conf.d/31_aide_nfs with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ssh-server with new version
Creating config file /etc/aide/aide.conf.d/31_aide_libapache2-mod-fastcgi with new version
Creating config file /etc/aide/aide.conf.d/31_aide_mlocate with new version
Creating config file /etc/aide/aide.conf.d/31_aide_uuidd-runtime with new version
Creating config file /etc/aide/aide.conf.d/31_aide_cracklib-runtime with new version
Creating config file /etc/aide/aide.conf.d/31_aide_redis with new version
Creating config file /etc/aide/aide.conf.d/70_aide_var with new version
Creating config file /etc/aide/aide.conf.d/31_aide_isc-dhcp-server with new version
Creating config file /etc/aide/aide.conf.d/30_aide_apache2 with new version
Creating config file /etc/aide/aide.conf.d/31_aide_ifupdown with new version
Creating config file /etc/aide/aide.conf.d/31_aide_awstats with new version
Creating config file /etc/aide/aide.conf with new version
Creating config file /etc/default/aide with new version
Creating config file /etc/cron.daily/dailyaidecheck with new version
Creating group '_aide' with GID 988.
Creating user '_aide' (Advanced Intrusion Detection Environment) with UID 988 and GID 988.
Created symlink /etc/systemd/system/timers.target.wants/dailyaidecheck.timer → /usr/lib/systemd/system/dailyaidecheck.timer.
dailyaidecheck.service is a disabled or a static unit, not starting it.
dailyaidecheck.service is a disabled or a static unit, not starting it.
Setting up bsd-mailx (8.1.2-0.20220412cvs-1build1) ...
update-alternatives: using /usr/bin/bsd-mailx to provide /usr/bin/mailx (mailx) in auto mode
Processing triggers for rsyslog (8.2312.0-3ubuntu9) ...
Processing triggers for ufw (0.36.2-6) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
Scanning processes...                                                              Scanning linux images...                                                           
Running kernel seems to be up-to-date.
No services need to be restarted.
No containers need to be restarted.
No user sessions are running outdated binaries.
No VM guests are running outdated hypervisor (qemu) binaries on this host.
```

What is being put in the path `/etc/aide/aide.conf.d/`?

```bash
10_aide_constants             31_aide_awstats                 31_aide_exim4_logs              31_aide_man                  31_aide_proftpd              31_aide_systemd-resolved
10_aide_distribution          31_aide_bandwidthd              31_aide_fail2ban                31_aide_mariadb              31_aide_redis                31_aide_systemd-timesyncd
10_aide_hostname              31_aide_bind9                   31_aide_fake-hwclock            31_aide_mdadm                31_aide_resolvconf           31_aide_systemd_sessions
10_aide_logext                31_aide_boinc-client            31_aide_fcron                   31_aide_mlocate              31_aide_rkhunter             31_aide_tiger
10_aide_machineid             31_aide_borgbackup              31_aide_findutils               31_aide_modules              31_aide_rngd                 31_aide_tlp
10_aide_prevyear              31_aide_btmp                    31_aide_gnupg                   31_aide_munin                31_aide_root-dotfiles        31_aide_tmux
10_aide_run                   31_aide_cereal                  31_aide_greylistd               31_aide_munin-node           31_aide_rsnapshot            31_aide_torrus
10_aide_year                  31_aide_checksecurity           31_aide_grub-efi                31_aide_munin-nodes          31_aide_rsyslog              31_aide_trac
20_aide_run_systemd-journald  31_aide_chrony                  31_aide_hald                    31_aide_mysql-server         31_aide_run_systemd_netif    31_aide_tt-rss
21_aide_run_agetty            31_aide_clamav                  31_aide_haproxy                 31_aide_needrestart          31_aide_run_systemd_resolve  31_aide_udev
21_aide_spamassassin          31_aide_clamav-freshclam        31_aide_hapsd                   31_aide_netdata              31_aide_run_tmpfiles         31_aide_ufw
30_aide_apache2               31_aide_clamav-unofficial-sigs  31_aide_haveged                 31_aide_network              31_aide_runuser              31_aide_unbound
30_aide_bind9                 31_aide_console-log             31_aide_icinga2                 31_aide_network-manager      31_aide_samba                31_aide_util-linux
30_inn2_vars                  31_aide_console-setup           31_aide_ifplugd                 31_aide_nfs                  31_aide_saslauthd            31_aide_utmp
31_aide_acpid                 31_aide_courier-authlib         31_aide_ifupdown                31_aide_nginx                31_aide_schroot              31_aide_uuidd-runtime
31_aide_adjtime               31_aide_cracklib-runtime        31_aide_inetd                   31_aide_nrpe                 31_aide_screen               31_aide_vpnc
31_aide_aide                  31_aide_cron                    31_aide_initramfs-tools         31_aide_nscd                 31_aide_slapd                31_aide_vsftpd
31_aide_alsa                  31_aide_cron-apt                31_aide_initscripts             31_aide_nslcd                31_aide_slrn                 31_aide_webalizer
31_aide_amanda-client         31_aide_cups                    31_aide_inn2                    31_aide_ntpsec               31_aide_smartmontools        31_aide_wpasupplicant
31_aide_amanda-server         31_aide_dbus                    31_aide_ippl                    31_aide_oidentd              31_aide_smokeping            31_aide_wtmp
31_aide_amavisd-new           31_aide_dcc-common              31_aide_irqbalance              31_aide_openvpn              31_aide_sniproxy             31_aide_x11-common
31_aide_anacron               31_aide_ddclient                31_aide_isc-dhcp-client         31_aide_openvpn-server       31_aide_snmpd                31_aide_x11-xkb-utils
31_aide_anubis                31_aide_debconf                 31_aide_isc-dhcp-server         31_aide_opie-server          31_aide_spamassassin         31_aide_xdm
31_aide_apache2               31_aide_debsecan                31_aide_kerberos                31_aide_pam_motd             31_aide_spampd               31_aide_xe-guest-utilities
31_aide_apache2-fcgid         31_aide_debspawn                31_aide_laptop-mode-tools       31_aide_pcscd                31_aide_squid                31_aide_xinetd
31_aide_apcupsd               31_aide_dehydrated              31_aide_lastlog                 31_aide_php-common           31_aide_ssh-agent            70_aide_dev
31_aide_apt                   31_aide_dev                     31_aide_libapache2-mod-fastcgi  31_aide_php-fpm              31_aide_ssh-server           70_aide_etc
31_aide_apt-cacher-ng         31_aide_dlocate                 31_aide_libvirt                 31_aide_php7                 31_aide_sudo                 70_aide_proc_sys
31_aide_apt-listbugs          31_aide_dmeventd                31_aide_lighttpd                31_aide_plocate              31_aide_svn-server           70_aide_run
31_aide_apt-listchanges       31_aide_dokuwiki                31_aide_lldpd                   31_aide_pm-utils             31_aide_syslog-ng            70_aide_tmp
31_aide_apt-show-versions     31_aide_dovecot                 31_aide_locales                 31_aide_portmap              31_aide_systemd              70_aide_var
31_aide_aptitude              31_aide_dpkg                    31_aide_logcheck                31_aide_postfix              31_aide_systemd-cron         99_aide_root
31_aide_asterisk              31_aide_e2fsprogs               31_aide_logrotate               31_aide_postfix-cluebringer  31_aide_systemd-journald
31_aide_at                    31_aide_etckeeper               31_aide_lpd                     31_aide_postgresql-15        31_aide_systemd-machined
31_aide_atop                  31_aide_exim4                   31_aide_lvm2                    31_aide_postgrey             31_aide_systemd-networkd
31_aide_avahi-daemon          31_aide_exim4_exiscan           31_aide_mail                    31_aide_privoxy              31_aide_systemd-nspawn
```

- How many files are in there?
	*ls -l /etc/aide/aide.conf.d/ | wc -l*
```bash
213
```

*aide -v

```bash
AIDE 0.18.6

Compile-time options:
use pcre2: mandatory
use pthread: yes
use zlib compression: yes
use POSIX ACLs: yes
use SELinux: yes
use xattr: yes
use POSIX 1003.1e capabilities: yes
use e2fsattrs: yes
use cURL: no
use Mhash: yes
use GNU crypto library: no
use Linux Auditing Framework: yes
use locale: no
syslog ident: aide
syslog logopt: LOG_CONS
syslog priority: LOG_NOTICE
default syslog facility: LOG_LOCAL0

Default config values:
config file: <none>
database_in: <none>
database_out: <none>

Available compiled-in attributes:
acl: yes
xattrs: yes
selinux: yes
e2fsattrs: yes
caps: yes

Available hashsum attributes:
md5: yes
sha1: yes
sha256: yes
sha512: yes
rmd160: yes
tiger: yes
crc32: yes
crc32b: yes
haval: yes
whirlpool: yes
gost: yes
stribog256: no
stribog512: no

Default compound groups:
R: l+p+u+g+s+c+m+i+n+md5+acl+selinux+xattrs+ftype+e2fsattrs+caps
L: l+p+u+g+i+n+acl+selinux+xattrs+ftype+e2fsattrs+caps
>: l+p+u+g+s+i+n+acl+selinux+xattrs+ftype+e2fsattrs+caps+growing
H: md5+sha1+rmd160+tiger+crc32+haval+gost+crc32b+sha256+sha512+whirlpool
X: acl+selinux+xattrs+e2fsattrs+caps
```

- What does aide try to do, and how does it do it?
	It checks the integrity of files by keeping a checksum of the files and comparing them afterward to see if they changed.

- What is the configuration of cron found in `/etc/cron.daily/dailyaidecheck`?

```bash
#!/bin/sh

# Skip if systemd is running.
if [ -d /run/systemd/system ]; then
    exit 0
fi

SCRIPT="/usr/share/aide/bin/dailyaidecheck"
if [ -x "${SCRIPT}" ]; then
    if command -v capsh >/dev/null; then
        capsh --caps="cap_dac_read_search,cap_audit_write+eip cap_setpcap,cap_setuid,cap_setgid+ep" --keep=1 --user=_aide --addamb=cap_dac_read_search,cap_audit_write -- -c "${SCRIPT} --crondaily"
    else
        # no capsh present, run with full capabilities
        "${SCRIPT}" --crondaily
    fi
fi
```


    - What does this attempt to do?
	    - run the daily aide check
    - What checks are there before execution?
	    - if the directory /run/systemd/system exist and 
    - Read the man for `capsh`, what is it used for?
	    - to test certain system capabilities and use them

*time aide -i -c /etc/aide/aide.conf*
```bash
Start timestamp: 2025-06-14 18:04:48 +0000 (AIDE 0.18.6)
AIDE successfully initialized database.
New AIDE database written to /var/lib/aide/aide.db.new
Ignored e2fs attributes: EINV

Number of entries:      127852

---------------------------------------------------
The attributes of the (uncompressed) database(s):
---------------------------------------------------

/var/lib/aide/aide.db.new
 MD5       : hwHEL1S/JH+lPTfQHtI0Tw==
 SHA1      : HfqRCq2tELhMBRIJXiwKfeD3rEc=
 SHA256    : HUEutbxkIk+BsKSV1YSgxMKLbqskqs4n
             iqecROgnrdg=
 SHA512    : 5mUAY7gs7ggffbaE+Aw/i+gzoEzh73aE
             ZfPLMHEuHguUAmxdOD9EcuSrsPhLOZ7a
             u4FqmopbvueGRYM+NH6Yzw==
 RMD160    : 8g+VNGOi0S+k3xwxIPPZhX10UmY=
 TIGER     : m1FTo9w03x4hMfzbSJBo8rwjbRj/q3Nl
 CRC32     : Lov7dw==
 CRC32B    : rco51g==
 HAVAL     : ujCsCg2nx8kQBT5RspR92cPiGGYRGF9u
             /HCYp8Xza8A=
 WHIRLPOOL : hg1EEqdlA74r4BkeSN8AjPSOCCgQTuHe
             IDadxzta+hQx3eyMy3OzhxZWpCZx/XMH
             ZqiEf3O2873+W6OWkaTAVw==
 GOST      : F6dzjjn6pBLgk40qB/FCPMBjbeMSq4/8
             tcZkrMaGDAU=


End timestamp: 2025-06-14 18:09:06 +0000 (run time: 4m 18s)

real    4m17.877s
user    3m28.225s
sys     0m9.166s
```

How long did that take?

- How much time was wall clock v. system/user time?
- Why might you want to know this on your systems?
- What do you notice about the output?
    1. What do you need to go read about?

*cp /var/lib/aide/aide.db.new /var/lib/aide/aide.db

*mkdir /root/prolug
touch /root/prolug/test1
touch /root/prolug/test2
time aide -c /etc/aide/aide.conf --check

```bash
Start timestamp: 2025-06-14 18:28:30 +0000 (AIDE 0.18.6)
AIDE found differences between database and filesystem!!
Ignored e2fs attributes: EINV

Summary:
  Total number of entries:      127855
  Added entries:                3
  Removed entries:              1
  Changed entries:              2

---------------------------------------------------
Added entries:
---------------------------------------------------

d+++++++++++++++++: /root/prolug
f+++++++++++++++++: /root/prolug/test1
f+++++++++++++++++: /root/prolug/test2

---------------------------------------------------
Removed entries:
---------------------------------------------------

d-----------------: /run/systemd/propagate/fwupd.service

---------------------------------------------------
Changed entries:
---------------------------------------------------

d =.... mc.n .. . : /root
f >b... mc..H.. . : /var/log/sysstat/sa14

---------------------------------------------------
Detailed information about changes:
---------------------------------------------------

Directory: /root
 Mtime     : 2025-06-10 08:19:00 +0000        | 2025-06-14 18:28:30 +0000
 Ctime     : 2025-06-10 08:19:00 +0000        | 2025-06-14 18:28:30 +0000
 Linkcount : 4                                | 5

File: /var/log/sysstat/sa14
 Size      : 7208                             | 8720
 Bcount    : 16                               | 24
 Mtime     : 2025-06-14 18:20:00 +0000        | 2025-06-14 18:30:15 +0000
 Ctime     : 2025-06-14 18:20:00 +0000        | 2025-06-14 18:30:15 +0000
 MD5       : EWTZYX7+5GGRgdmNO2Hs0A==         | mvaYZh+zUVZH+2YqAT2aXg==
 SHA1      : tTHdaR937NofFHCP5jfF6LGc9yE=     | BiouDJpnb9qJ1OjwJCu3Y3H8KYM=
 SHA256    : uU0F8iDfkYwX9/Io9AfY7/FULkmLBnSS | d+U/eVrRebqSp2yyE8mspdM1E6mcxjtk
             Be9WA2zFzmQ=                     | TA7MQfcpMl8=
 SHA512    : Ul8ugvhIi2R1OxESfuD8Vr6nbS++VDgi | Wuj8aniwNRDTHwJp7CgGjFq4KlFdlnqo
             CZaazdDWVj/LIdJ53h0lKTFhjtLIS/8K | 2PpK6rGRssCR6o5YHyak+Uu0bcWKu0aC
             lIY1WLeRoKoxMFc6MXQ6bg==         | 0D4LWNONWntwFuVyoAKXrA==
 RMD160    : dmQbKbqq+wMubiGXqwuRAGxcV1c=     | ikd70Bjq607KeMdNxesLXPxgxkY=
 TIGER     : po5xUQQ8GrRHc9IZ2ExtszEXdnW14pAx | TfUDRD32LPJGUPT1c5MnXhSLhIortwr8
 CRC32     : 8QcSzw==                         | QPp2yQ==
 CRC32B    : TqMV9g==                         | 71g4Hg==
 HAVAL     : lU6KV7/DzqYX1l1twM9ypbdDPAZISMs9 | /0TXhLrlqgwsXoUKPSq76DZDSNbZdRYF
             GLRxa/BNdUs=                     | w7GxKSE/YYU=
 WHIRLPOOL : UQhhDn92MF+BOA152zS+peNeJDofyhCo | r3odwdu4dmMKVCVaGq/koJAHCiJrGpeP
             tr71aFYSLMNhMk/t5XueECTKLd3eYpWx | HPc9HHpf+SKPxpDjeAXp4gcO7gM2BwpY
             gfedLs76jV3PDVTElT1GhQ==         | jAZqUaPXMGQneGBe84+HiA==
 GOST      : 7z4GVNIhu2Em51Pq6d6hm781Hukepina | c/C05cA6pMhF9Db5yjkxrmrxzha1hlkT
             GehKHK7594k=                     | KIRFO/d86aw=


---------------------------------------------------
The attributes of the (uncompressed) database(s):
---------------------------------------------------

/var/lib/aide/aide.db
 MD5       : k8T3RYVqhR/KzCeQF4yUvQ==
 SHA1      : phCBa/Jy/iGjvaDikBd9NQOYoxI=
 SHA256    : bkXp5UcIZrwwSFLQcNB4X0FHn29Kw6jU
             yOSM6ErWjRM=
 SHA512    : A83Rl5HWYsR1p7eyz6wBScKyc+WfHnTv
             ho2MkxdoABZELPhKQDKj+VuWEc1+3/cb
             mPpMn27aluqUDp4pCXwypg==
 RMD160    : GS+oHL5Bj20VY3h6FJc0CeQynxw=
 TIGER     : ERu28eywam8AHwO5NKRbrukcXPMzxY+X
 CRC32     : lctlfg==
 CRC32B    : QmqSVQ==
 HAVAL     : CE8bqBOqSHGnDT4cfeZPdj5Wqp5GvKyW
             09u4KvHoxJE=
 WHIRLPOOL : QZiSu5PKnELRzQFBUZAUbCM7oDUfAXt+
             ztbMCqRk+DyeoecAhuXo8yupGKbRNMI5
             UHlkpZ0LBcQE6UpDfGVwgA==
 GOST      : 3TN61P0ON/qS9nOiGUsdVpxWpcrHOPN9
             9ngvGOZO6q4=


End timestamp: 2025-06-14 18:36:37 +0000 (run time: 8m 7s)

real    8m6.884s
user    7m6.880s
sys     0m11.642s
```
- Did you see your new files created? 
	yes
- How long did this take to run?
    1. What type of usage do you see against user/system space?

*cat /root/hosts*
```bash
[servers]
controlplane env=prod app=db
node01 env=dev app=web

[webservers]
node01 env=dev app=web
```

*ls /answers/*
```bash
dev_index.html  dev_virtual_host.conf  individual_web_environment.yaml  qa_index.html  qa_virtual_host.conf  test_index.html  test_virtual_host.conf  web_environment.yaml
```

*cat /answers/dev_index.html*
```html
<html>
<head><title>Dev Page</title><head>
<body>Dev Environment</body>
```

*cat /answers/dev_virtual_host.conf*
```nginx
<VirtualHost *:8080>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html_dev

        ErrorLog ${APACHE_LOG_DIR}/dev_error.log
        CustomLog ${APACHE_LOG_DIR}/dev_access.log combined
```

*cat /answer/individual_web_environment.yaml*
```yaml
---
#Required variables:
#deploy = present or absent
#env = dev test or qa
#port = 8080 8081 or 8082 (must match defined spec given by teams)

- name: Web Environment
  hosts: webservers
  vars:
  gather_facts: True
  become: True
  tasks:

  - name: Install Apache2 Server
    apt:
      name: "apache2"
      state: latest

  - name: Block for Present deploy State
    when: deploy == "present"
    block:

    - name: Create directories for environments
      file:
        path: "/var/www/html_{{env}}"
        state: directory
      notify:
        - Restart apache
    
    - name: Add the Listener ports to /etc/apache2/ports.conf
      lineinfile:
        path: /etc/apache2/ports.conf
        insertafter: '^Listen'
        state: present
        line: "Listen {{port}}"
      notify:
        - Restart apache

    - name: Push the Virtual Directives files into the correct place
      copy:
        src: "/answers/{{env}}_virtual_host.conf"
        dest: "/etc/apache2/sites-enabled/{{env}}_virtual_host.conf"
      notify:
        - Restart apache

    - name: Push the html for each page over
      copy:
        src: "/answers/{{env}}_index.html"
        dest: "/var/www/html_{{env}}/index.html"
      notify:
        - Restart apache

  - name: Block for Absent deploy State
    when: deploy == "absent"
    block:

    - name: Delete directories for environments
      file:
        path: "/var/www/html_{{env}}"
        state: absent     
      notify:
        - Restart apache
    
    - name: Remove the Listener ports to /etc/apache2/ports.conf
      lineinfile:
        path: /etc/apache2/ports.conf
        insertafter: '^Listen'
        state: absent
        line: "Listen {{port}}"
      loop:
      notify:
        - Restart apache

    - name: Remove the Virtual Directives files into the correct place
      file:
        path: "/var/www/html_{{env}}/index.html"
        state: absent
      notify:
        - Restart apache

  handlers:

  - name: Restart apache
    systemd:
      state: restarted
      name: apache2
```

*cat /answers/qa_index.html*
```html
<html>
<head><title>QA Page</title><head>
<body>QA Environment</body>
```

*cat /etc/qa_virtual_host.conf*
```nginx
<VirtualHost *:8082>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html_qa

        ErrorLog ${APACHE_LOG_DIR}/qa_error.log
        CustomLog ${APACHE_LOG_DIR}/qa_access.log combined
```

*cat /answers/test_index.html*
```html
<html>
<head><title>Test Page</title><head>
<body>Test Environment</body>
```

*cat /answers/test_virtual_host.conf*
```nginx
<VirtualHost *:8081>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html_test

        ErrorLog ${APACHE_LOG_DIR}/test_error.log
        CustomLog ${APACHE_LOG_DIR}/test_access.log combined
```

*cat /answers/web_environment.yaml*
```yaml
---

- name: Web Environment
  hosts: webservers
  vars:
  gather_facts: True
  become: True
  tasks:

  - name: Install Apache2 Server
    apt:
      name: "apache2"
      state: latest
    
  - name: Create directories for environments
    file:
      path: "/var/www/html_{{item}}"
      state: directory
    loop:
    - dev
    - test
    - qa
    notify:
      - Restart apache
  
  - name: Add the Listener ports to /etc/apache2/ports.conf
    lineinfile:
      path: /etc/apache2/ports.conf
      insertafter: '^Listen'
      state: present
      line: "{{item}}"
    loop:
    - 'Listen 8080'
    - 'Listen 8081'
    - 'Listen 8082'
    notify:
      - Restart apache

  - name: Push the Virtual Directives files into the correct place
    copy:
      src: "/answers/{{item}}"
      dest: "/etc/apache2/sites-enabled/{{item}}"
    loop:
    - dev_virtual_host.conf
    - qa_virtual_host.conf
    - test_virtual_host.conf
    notify:
      - Restart apache

  - name: Push the html for each page over
    copy:
      src: "/answers/{{item.name}}"
      dest: "/var/www/html_{{item.env}}/index.html"
    loop:
    - { env: 'dev', name: 'dev_index.html'}
    - { env: 'test', name: 'test_index.html'}
    - { env: 'qa', name: 'qa_index.html'}
    notify:
      - Restart apache

  handlers:

  - name: Restart apache
    systemd:
      state: restarted
      name: apache2
```

*ansible-playbook -i /root/hosts /root/web_environment.yaml*
```yaml
PLAY [Web Environment] ********************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [node01]

TASK [Install Apache2 Server] *************************************************************************************************************************************************************
changed: [node01]

TASK [Create directories for environments] ************************************************************************************************************************************************
changed: [node01] => (item=dev)
changed: [node01] => (item=test)
changed: [node01] => (item=qa)

TASK [Add the Listener ports to /etc/apache2/ports.conf] **********************************************************************************************************************************
changed: [node01] => (item=Listen 8080)
changed: [node01] => (item=Listen 8081)
changed: [node01] => (item=Listen 8082)

TASK [Push the Virtual Directives files into the correct place] ***************************************************************************************************************************
changed: [node01] => (item=dev_virtual_host.conf)
changed: [node01] => (item=qa_virtual_host.conf)
changed: [node01] => (item=test_virtual_host.conf)

TASK [Push the html for each page over] ***************************************************************************************************************************************************
changed: [node01] => (item={'env': 'dev', 'name': 'dev_index.html'})
changed: [node01] => (item={'env': 'test', 'name': 'test_index.html'})
changed: [node01] => (item={'env': 'qa', 'name': 'qa_index.html'})

RUNNING HANDLER [Restart apache] **********************************************************************************************************************************************************
changed: [node01]

PLAY RECAP ********************************************************************************************************************************************************************************
node01                     : ok=7    changed=6    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

```yaml
PLAY [Web Environment] ********************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [node01]

TASK [Install Apache2 Server] *************************************************************************************************************************************************************
ok: [node01]

TASK [Create directories for environments] ************************************************************************************************************************************************
ok: [node01] => (item=dev)
ok: [node01] => (item=test)
ok: [node01] => (item=qa)

TASK [Add the Listener ports to /etc/apache2/ports.conf] **********************************************************************************************************************************
ok: [node01] => (item=Listen 8080)
ok: [node01] => (item=Listen 8081)
ok: [node01] => (item=Listen 8082)

TASK [Push the Virtual Directives files into the correct place] ***************************************************************************************************************************
ok: [node01] => (item=dev_virtual_host.conf)
ok: [node01] => (item=qa_virtual_host.conf)
ok: [node01] => (item=test_virtual_host.conf)

TASK [Push the html for each page over] ***************************************************************************************************************************************************
ok: [node01] => (item={'env': 'dev', 'name': 'dev_index.html'})
ok: [node01] => (item={'env': 'test', 'name': 'test_index.html'})
ok: [node01] => (item={'env': 'qa', 'name': 'qa_index.html'})

PLAY RECAP ********************************************************************************************************************************************************************************
node01                     : ok=6    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

Did the handler run the second time?  no
Why or why not? There was no change in the playbook / configurations

*curl node01:8080*
```html
<html>
<head><title>Dev Page</title><head>
<body>Dev Environment</body>
</html>
```

curl node01:8081
```html
<html>
<head><title>Test Page</title><head>
<body>Test Environment</body>
</html>
```

*curl node01:8082*
```html
<html>
<head><title>QA Page</title><head>
<body>QA Environment</body>
```

*ansible-playbook -i /root/hosts /root/individual_web_environment.yaml --extra-vars "deploy=absent env=test port=8081"*
```yaml
[WARNING]: Found variable using reserved name: port

PLAY [Web Environment] ********************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [node01]

TASK [Install Apache2 Server] *************************************************************************************************************************************************************
ok: [node01]

TASK [Create directories for environments] ************************************************************************************************************************************************
skipping: [node01]

TASK [Add the Listener ports to /etc/apache2/ports.conf] **********************************************************************************************************************************
skipping: [node01]

TASK [Push the Virtual Directives files into the correct place] ***************************************************************************************************************************
skipping: [node01]

TASK [Push the html for each page over] ***************************************************************************************************************************************************
skipping: [node01]

TASK [Delete directories for environments] ************************************************************************************************************************************************
changed: [node01]

TASK [Remove the Listener ports to /etc/apache2/ports.conf] *******************************************************************************************************************************
changed: [node01]

TASK [Remove the Virtual Directives files into the correct place] *************************************************************************************************************************
ok: [node01]

RUNNING HANDLER [Restart apache] **********************************************************************************************************************************************************
changed: [node01]

PLAY RECAP ********************************************************************************************************************************************************************************
node01                     : ok=6    changed=3    unreachable=0    failed=0    skipped=4    rescued=0    ignored=0
```

*curl node01:8081*
```bash
curl: (7) Failed to connect to node01 port 8081 after 1 ms: Couldn't connect to server
```

*ansible-playbook -i /root/hosts /root/web_environment.yaml*
```yaml
PLAY [Web Environment] ********************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [node01]

TASK [Install Apache2 Server] *************************************************************************************************************************************************************
ok: [node01]

TASK [Create directories for environments] ************************************************************************************************************************************************
ok: [node01] => (item=dev)
changed: [node01] => (item=test)
ok: [node01] => (item=qa)

TASK [Add the Listener ports to /etc/apache2/ports.conf] **********************************************************************************************************************************
ok: [node01] => (item=Listen 8080)
changed: [node01] => (item=Listen 8081)
ok: [node01] => (item=Listen 8082)

TASK [Push the Virtual Directives files into the correct place] ***************************************************************************************************************************
ok: [node01] => (item=dev_virtual_host.conf)
ok: [node01] => (item=qa_virtual_host.conf)
ok: [node01] => (item=test_virtual_host.conf)

TASK [Push the html for each page over] ***************************************************************************************************************************************************
ok: [node01] => (item={'env': 'dev', 'name': 'dev_index.html'})
changed: [node01] => (item={'env': 'test', 'name': 'test_index.html'})
ok: [node01] => (item={'env': 'qa', 'name': 'qa_index.html'})

RUNNING HANDLER [Restart apache] **********************************************************************************************************************************************************
changed: [node01]

PLAY RECAP ********************************************************************************************************************************************************************************
node01                     : ok=7    changed=4    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

- Did this force the system back into a working configuration? yes
    - If it worked, would it always work, or would they (the systems) need to be manually intervened? It will return the configuration to the one in the playbook.
    - What is your test? (hint: `curl` the ports `8080`, `8081`, and `8082` from previous commands) curl localhost:8081
- Could this cause potential problems in the environment? yes
    - If so, is that problem based on technology or operational practices? Why
		Operational practice can cause operational problems because 


