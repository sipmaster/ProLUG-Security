cat /etc/*release
NAME="Rocky Linux"
VERSION="9.5 (Blue Onyx)"
ID="rocky"
ID_LIKE="rhel centos fedora"
VERSION_ID="9.5"
PLATFORM_ID="platform:el9"
PRETTY_NAME="Rocky Linux 9.5 (Blue Onyx)"
ANSI_COLOR="0;32"
LOGO="fedora-logo-icon"
CPE_NAME="cpe:/o:rocky:rocky:9::baseos"
HOME_URL="https://rockylinux.org/"
VENDOR_NAME="RESF"
VENDOR_URL="https://resf.org/"
BUG_REPORT_URL="https://bugs.rockylinux.org/"
SUPPORT_END="2032-05-31"
ROCKY_SUPPORT_PRODUCT="Rocky-Linux-9"
ROCKY_SUPPORT_PRODUCT_VERSION="9.5"
REDHAT_SUPPORT_PRODUCT="Rocky Linux"
REDHAT_SUPPORT_PRODUCT_VERSION="9.5"
Rocky Linux release 9.5 (Blue Onyx)
Rocky Linux release 9.5 (Blue Onyx)
Rocky Linux release 9.5 (Blue Onyx)

uname
uname -a
uname -r
Linux
Linux rocky19 5.14.0-427.42.1.el9_4.x86_64 #1 SMP PREEMPT_DYNAMIC Thu Oct 31 14:01:51 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux
5.14.0-427.42.1.el9_4.x86_64

cat /proc/meminfo
MemTotal:        3985428 kB
MemFree:         1455556 kB
MemAvailable:    1396348 kB
Buffers:            1044 kB
Cached:          2142960 kB
SwapCached:            0 kB
Active:          2250344 kB
Inactive:           1088 kB
Active(anon):    2198336 kB
Inactive(anon):        0 kB
Active(file):      52008 kB
Inactive(file):     1088 kB
Unevictable:           0 kB
Mlocked:               0 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Zswap:                 0 kB
Zswapped:              0 kB
Dirty:                 0 kB
Writeback:             0 kB
AnonPages:        105492 kB
Mapped:           107584 kB
Shmem:           2090908 kB
KReclaimable:      62412 kB
Slab:             179224 kB
SReclaimable:      62412 kB
SUnreclaim:       116812 kB
KernelStack:        3184 kB
PageTables:         2124 kB
SecPageTables:         0 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:     1992712 kB
Committed_AS:    2628012 kB
VmallocTotal:   34359738367 kB
VmallocUsed:       33912 kB
VmallocChunk:          0 kB
Percpu:            26368 kB
HardwareCorrupted:     0 kB
AnonHugePages:     45056 kB
ShmemHugePages:        0 kB
ShmemPmdMapped:        0 kB
FileHugePages:         0 kB
FilePmdMapped:         0 kB
CmaTotal:              0 kB
CmaFree:               0 kB
Unaccepted:            0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
Hugetlb:               0 kB
DirectMap4k:      133120 kB
DirectMap2M:     3004416 kB
DirectMap1G:     1048576 kB

free
               total        used        free      shared  buff/cache   available
Mem:         3985428     2589080     1455556     2090908     2206416     1396348
Swap:              0           0           0

free -m
               total        used        free      shared  buff/cache   available
Mem:            3892        2528        1421        2041        2154        1363
Swap:              0           0           0

cat /proc/cpuinfo
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 45
model name      : Intel(R) Xeon(R) CPU E5-2665 0 @ 2.40GHz
stepping        : 7
microcode       : 0x71a
cpu MHz         : 2400.014
cache size      : 20480 KB
physical id     : 0
siblings        : 1
core id         : 0
cpu cores       : 1
apicid          : 0
initial apicid  : 0
fpu             : yes
fpu_exception   : yes
cpuid level     : 13
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush acpi mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx hypervisor lahf_lm cpuid_fault pti ssbd ibrs ibpb stibp xsaveopt md_clear flush_l1d
bugs            : cpu_meltdown spectre_v1 spectre_v2 spec_store_bypass l1tf mds swapgs itlb_multihit mmio_unknown bhi
bogomips        : 4800.02
clflush size    : 64
cache_alignment : 64
address sizes   : 46 bits physical, 48 bits virtual
power management:

processor       : 1
vendor_id       : GenuineIntel
cpu family      : 6
model           : 45
model name      : Intel(R) Xeon(R) CPU E5-2665 0 @ 2.40GHz
stepping        : 7
microcode       : 0x71a
cpu MHz         : 2400.014
cache size      : 20480 KB
physical id     : 1
siblings        : 1
core id         : 0
cpu cores       : 1
apicid          : 2
initial apicid  : 2
fpu             : yes
fpu_exception   : yes
cpuid level     : 13
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush acpi mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer aes xsave avx hypervisor lahf_lm cpuid_fault pti ssbd ibrs ibpb stibp xsaveopt md_clear flush_l1d
bugs            : cpu_meltdown spectre_v1 spectre_v2 spec_store_bypass l1tf mds swapgs itlb_multihit mmio_unknown bhi
bogomips        : 4800.02
clflush size    : 64
cache_alignment : 64
address sizes   : 46 bits physical, 48 bits virtual
power management:

cat /proc/cpuinfo | grep proc | wc -l
2

df
Filesystem               1K-blocks     Used Available Use% Mounted on
devtmpfs                      4096        0      4096   0% /dev
tmpfs                      1992712        0   1992712   0% /dev/shm
tmpfs                      1992712     8712   1984000   1% /run
tmpfs                      8388608  2073952   6314656  25% /
tmpfs                      1992712        0   1992712   0% /run/shm
192.168.200.25:/labs     203345920 46540800 156805120  23% /labs
192.168.200.25:/home     203345920 46540800 156805120  23% /home
192.168.200.25:/lab_work 203345920 46540800 156805120  23% /lab_work
192.168.200.25:/opt      203345920 46540800 156805120  23% /opt
tmpfs                       398540        0    398540   0% /run/user/0

df -h
Filesystem                Size  Used Avail Use% Mounted on
devtmpfs                  4.0M     0  4.0M   0% /dev
tmpfs                     2.0G     0  2.0G   0% /dev/shm
tmpfs                     2.0G  8.6M  1.9G   1% /run
tmpfs                     8.0G  2.0G  6.1G  25% /
tmpfs                     2.0G     0  2.0G   0% /run/shm
192.168.200.25:/labs      194G   45G  150G  23% /labs
192.168.200.25:/home      194G   45G  150G  23% /home
192.168.200.25:/lab_work  194G   45G  150G  23% /lab_work
192.168.200.25:/opt       194G   45G  150G  23% /opt
tmpfs                     390M     0  390M   0% /run/user/0

df -h | grep -i var

df -h | grep -i sd

mount
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
sysfs on /sys type sysfs (rw,relatime,seclabel)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=4096k,nr_inodes=489325,mode=755,inode64)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel,inode64)
devpts on /dev/pts type devpts (rw,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,size=797088k,nr_inodes=819200,mode=755,inode64)
cgroup2 on /sys/fs/cgroup type cgroup2 (rw,nosuid,nodev,noexec,relatime,seclabel,nsdelegate,memory_recursiveprot)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime,seclabel)
bpf on /sys/fs/bpf type bpf (rw,nosuid,nodev,noexec,relatime,mode=700)
tmpfs on / type tmpfs (rw,relatime,seclabel,size=8388608k,inode64)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
proc on /proc type proc (rw,relatime)
tmpfs on /run type tmpfs (rw,relatime,seclabel,inode64)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,nosuid,noexec,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=30,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=18928)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel,pagesize=2M)
debugfs on /sys/kernel/debug type debugfs (rw,nosuid,nodev,noexec,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime,seclabel)
tracefs on /sys/kernel/tracing type tracefs (rw,nosuid,nodev,noexec,relatime,seclabel)
fusectl on /sys/fs/fuse/connections type fusectl (rw,nosuid,nodev,noexec,relatime)
configfs on /sys/kernel/config type configfs (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysusers.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-sysctl.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup-dev.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
tmpfs on /run/shm type tmpfs (rw,relatime,seclabel,inode64)
none on /run/credentials/systemd-tmpfiles-setup.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
192.168.200.25:/labs on /labs type nfs4 (rw,relatime,vers=4.2,rsize=1048576,wsize=1048576,namlen=255,hard,proto=tcp,timeo=600,retrans=2,sec=sys,clientaddr=192.168.200.69,local_lock=none,addr=192.168.200.25)
192.168.200.25:/home on /home type nfs4 (rw,relatime,vers=4.2,rsize=1048576,wsize=1048576,namlen=255,hard,proto=tcp,timeo=600,retrans=2,sec=sys,clientaddr=192.168.200.69,local_lock=none,addr=192.168.200.25)
192.168.200.25:/lab_work on /lab_work type nfs4 (rw,relatime,vers=4.2,rsize=1048576,wsize=1048576,namlen=255,hard,proto=tcp,timeo=600,retrans=2,sec=sys,clientaddr=192.168.200.69,local_lock=none,addr=192.168.200.25)
192.168.200.25:/opt on /opt type nfs4 (rw,relatime,vers=4.2,rsize=1048576,wsize=1048576,namlen=255,hard,proto=tcp,timeo=600,retrans=2,sec=sys,clientaddr=192.168.200.69,local_lock=none,addr=192.168.200.25)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=398540k,nr_inodes=99635,mode=700,inode64)

mount | grep -i home
192.168.200.25:/home on /home type nfs4 (rw,relatime,vers=4.2,rsize=1048576,wsize=1048576,namlen=255,hard,proto=tcp,timeo=600,retrans=2,sec=sys,clientaddr=192.168.200.69,local_lock=none,addr=192.168.200.25)

mount | grep -i /home/xgqa6cha

df -h /home/xgqa6cha
df: /home/xgqa6cha: No such file or directory

cd ~; pwd; df -h .
/root
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           8.0G  2.0G  6.1G  25% /

du -sh .
64K     .

du -h .
0       ./.ansible/tmp
0       ./.ansible
4.0K    ./.ssh
64K     .

uptime
13:14:15 up 4 days, 23:48,  1 user,  load average: 0.00, 0.00, 0.00

last
root     pts/0        192.168.11.245   Mon Apr 14 17:39   still logged in
root     pts/0        192.168.11.245   Mon Apr 14 12:56 - 13:14  (00:17)
root     pts/0        192.168.200.25   Sun Apr 13 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Sun Apr 13 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Sat Apr 12 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Sat Apr 12 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Sat Apr 12 15:29 - 15:31  (00:01)
root     pts/0        192.168.200.25   Fri Apr 11 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Fri Apr 11 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Fri Apr 11 22:35 - 22:35  (00:00)
root     pts/0        192.168.200.25   Fri Apr 11 22:35 - 22:35  (00:00)
root     pts/0        192.168.200.25   Fri Apr 11 21:25 - 21:25  (00:00)
root     pts/0        192.168.200.25   Thu Apr 10 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Thu Apr 10 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Wed Apr  9 23:55 - 23:55  (00:00)
root     pts/0        192.168.200.25   Wed Apr  9 23:55 - 23:55  (00:00)
reboot   system boot  5.14.0-427.42.1. Wed Apr  9 13:27   still running

 w
 17:40:28 up 5 days,  4:15,  1 user,  load average: 0.02, 0.01, 0.00
USER     TTY        LOGIN@   IDLE   JCPU   PCPU WHAT
root     pts/0     17:39    1.00s  0.03s  0.00s w

who
root     pts/0        2025-04-14 17:39 (192.168.11.245)

whoami
root

printenv
SHELL=/bin/bash
HISTCONTROL=ignoredups
HISTSIZE=1000
HOSTNAME=rocky19
PWD=/root
LOGNAME=root
XDG_SESSION_TYPE=tty
MOTD_SHOWN=pam
HOME=/root
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=01;37;41:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=01;36:*.au=01;36:*.flac=01;36:*.m4a=01;36:*.mid=01;36:*.midi=01;36:*.mka=01;36:*.mp3=01;36:*.mpc=01;36:*.ogg=01;36:*.ra=01;36:*.wav=01;36:*.oga=01;36:*.opus=01;36:*.spx=01;36:*.xspf=01;36:
SSH_CONNECTION=192.168.11.245 48202 192.168.200.69 22
XDG_SESSION_CLASS=user
SELINUX_ROLE_REQUESTED=
TERM=xterm
LESSOPEN=||/usr/bin/lesspipe.sh %s
USER=root
SELINUX_USE_CURRENT_RANGE=
SHLVL=1
XDG_SESSION_ID=25
XDG_RUNTIME_DIR=/run/user/0
S_COLORS=auto
SSH_CLIENT=192.168.11.245 48202 22
which_declare=declare -f
PATH=/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin
SELINUX_LEVEL_REQUESTED=
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/0/bus
MAIL=/var/spool/mail/root
SSH_TTY=/dev/pts/0
BASH_FUNC_which%%=() {  ( alias;
 eval ${which_declare} ) | /usr/bin/which --tty-only --read-alias --read-functions --show-tilde --show-dot $@
}
_=/usr/bin/printenv

printenv | grep -i home
HOME=/root

whoami
root

id
uid=0(root) gid=0(root) groups=0(root) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023

free -m
               total        used        free      shared  buff/cache   available
Mem:            3892        2531        1418        2041        2154        1360
Swap:              0           0           0

free -m | egrep 'Mem|Swap'
Mem:            3892        2531        1418        2041        2154        1360
Swap:              0           0           0

free -m| egrep "Mem|Swap" | awk '{print $1, $2, $3}'
Mem: 3892 2531
Swap: 0 0

free -t | egrep "Mem|Swap" | awk '{print $1 " Used Space = " ($3 / $2) * 100"%"}'
Mem: Used Space = 65.0428%
awk: cmd. line:1: (FILENAME=- FNR=2) fatal: division by zero attempted

for i in `seq 1 20`; do echo "I am counting i and am on $i times through the loop"; done
I am counting i and am on 1 times through the loop
I am counting i and am on 2 times through the loop
I am counting i and am on 3 times through the loop
I am counting i and am on 4 times through the loop
I am counting i and am on 5 times through the loop
I am counting i and am on 6 times through the loop
I am counting i and am on 7 times through the loop
I am counting i and am on 8 times through the loop
I am counting i and am on 9 times through the loop
I am counting i and am on 10 times through the loop
I am counting i and am on 11 times through the loop
I am counting i and am on 12 times through the loop
I am counting i and am on 13 times through the loop
I am counting i and am on 14 times through the loop
I am counting i and am on 15 times through the loop
I am counting i and am on 16 times through the loop
I am counting i and am on 17 times through the loop
I am counting i and am on 18 times through the loop
I am counting i and am on 19 times through the loop
I am counting i and am on 20 times through the loop

