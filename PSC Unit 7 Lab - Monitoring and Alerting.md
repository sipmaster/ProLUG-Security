```bash
fail2ban-client --version
Fail2Ban v1.0.2
```
```bash
tail -20 /var/log/fail2ban.log
2025-06-17 02:08:42,166 fail2ban.filter         [37366]: INFO      maxLines: 1
2025-06-17 02:08:42,183 fail2ban.filtersystemd  [37366]: INFO    [sshd] Added journal match for: '_SYSTEMD_UNIT=sshd.service + _COMM=sshd'
2025-06-17 02:08:42,183 fail2ban.filter         [37366]: INFO      maxRetry: 5
2025-06-17 02:08:42,183 fail2ban.filter         [37366]: INFO      findtime: 10
2025-06-17 02:08:42,183 fail2ban.actions        [37366]: INFO      banTime: 14400
2025-06-17 02:08:42,184 fail2ban.filter         [37366]: INFO      encoding: UTF-8
2025-06-17 02:08:42,185 fail2ban.jail           [37366]: INFO    Jail 'sshd' started
2025-06-17 02:08:42,186 fail2ban.filtersystemd  [37366]: INFO    [sshd] Jail is in operation now (process new journal entries)
2025-06-17 02:09:09,450 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:08
2025-06-17 02:09:11,405 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:11
2025-06-17 02:09:13,612 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:13
2025-06-17 02:09:14,654 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:14
2025-06-17 02:09:31,655 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:31
2025-06-17 02:09:32,904 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:32
2025-06-17 02:09:33,904 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:33
2025-06-17 02:09:34,654 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:34
2025-06-17 02:09:36,860 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:36
2025-06-17 02:09:37,327 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:36
2025-06-17 02:09:37,328 fail2ban.filter         [37366]: INFO    [sshd] Found 10.244.8.143 - 2025-06-17 02:09:37
2025-06-17 02:09:37,405 fail2ban.actions        [37366]: NOTICE  [sshd] Ban 10.244.8.143
```
```bash
fail2ban-client get sshd banned
['10.244.8.143']
```
```bash
fail2ban-client set sshd unbanip 10.244.8.143
1
```

![[Pasted image 20250616222414.png]]

![[Pasted image 20250616222553.png]]

```bash
tail -20 /var/log/fail2ban.log
2025-06-17 02:33:00,699 fail2ban.server         [42805]: INFO    Starting Fail2ban v1.0.2
2025-06-17 02:33:00,699 fail2ban.observer       [42805]: INFO    Observer start...
2025-06-17 02:33:00,702 fail2ban.database       [42805]: INFO    Connected to fail2ban persistent database '/var/lib/fail2ban/fail2ban.sqlite3'
2025-06-17 02:33:00,704 fail2ban.jail           [42805]: INFO    Creating new jail 'sshd'
2025-06-17 02:33:00,836 fail2ban.jail           [42805]: INFO    Jail 'sshd' uses systemd {}
2025-06-17 02:33:00,837 fail2ban.jail           [42805]: INFO    Initiated 'systemd' backend
2025-06-17 02:33:00,838 fail2ban.filter         [42805]: INFO      maxLines: 1
2025-06-17 02:33:00,855 fail2ban.filtersystemd  [42805]: INFO    [sshd] Added journal match for: '_SYSTEMD_UNIT=sshd.service + _COMM=sshd'
2025-06-17 02:33:00,855 fail2ban.filter         [42805]: INFO      maxRetry: 5
2025-06-17 02:33:00,855 fail2ban.filter         [42805]: INFO      findtime: 10
2025-06-17 02:33:00,855 fail2ban.actions        [42805]: INFO      banTime: 14400
2025-06-17 02:33:00,856 fail2ban.filter         [42805]: INFO      encoding: UTF-8
2025-06-17 02:33:00,857 fail2ban.jail           [42805]: INFO    Jail 'sshd' started
2025-06-17 02:33:00,857 fail2ban.filtersystemd  [42805]: INFO    [sshd] Jail is in operation now (process new journal entries)
2025-06-17 02:33:11,366 fail2ban.filter         [42805]: INFO    [sshd] Found 10.244.5.61 - 2025-06-17 02:33:10
2025-06-17 02:33:13,575 fail2ban.filter         [42805]: INFO    [sshd] Found 10.244.5.61 - 2025-06-17 02:33:13
2025-06-17 02:33:14,312 fail2ban.filter         [42805]: INFO    [sshd] Found 10.244.5.61 - 2025-06-17 02:33:13
2025-06-17 02:33:14,313 fail2ban.filter         [42805]: INFO    [sshd] Found 10.244.5.61 - 2025-06-17 02:33:14
2025-06-17 02:33:14,568 fail2ban.filter         [42805]: INFO    [sshd] Found 10.244.5.61 - 2025-06-17 02:33:14
2025-06-17 02:33:14,863 fail2ban.actions        [42805]: NOTICE  [sshd] Ban 10.244.5.61
controlplane:~$ fail2ban-client get sshd banned
['10.244.5.61']
controlplane:~$ fail2ban-client set sshd unbanip 10.244.5.61
1
```
```bash
ss -ntulp | grep 8086
tcp   LISTEN 0      4096                                    *:8086             *:*    users:(("influxd",pid=47542,fd=9))                    
controlplane:~$ lsof -i :8086
COMMAND   PID     USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
influxd 47542 influxdb    9u  IPv6 240479      0t0  TCP *:8086 (LISTEN)
```
```bash
nXuNcIcXu4iZL4Yx-Yb3lc_j4FjmXCl1mIVs7_URE4eo1AADDib0fKGD8u88bSBWVnxdXYpGgVIiQRXCb5sf4Q==
```
```bash
sudo -l -U telegraf
Matching Defaults entries for telegraf on controlplane:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin, use_pty

Runas and Command-specific defaults for telegraf:
    Defaults!/usr/bin/fail2ban-client status, /usr/bin/fail2ban-client status * !logfile, !syslog, !pam_session

User telegraf may run the following commands on controlplane:
    (root) NOEXEC: NOPASSWD: /usr/bin/fail2ban-client status, /usr/bin/fail2ban-client status *
```

![[Pasted image 20250616232654.png]]
