```bash
mkdir /var/chroot
```
```bash
mkdir -p /var/chroot/{bin,lib64,dev,etc,home,usr/bin,lib/x86_64-linux-gnu}
```
```bash
ls -l /var/chroot
```
```bash
total 28
drwxr-xr-x 2 root root 4096 Jun 15 02:46 bin
drwxr-xr-x 2 root root 4096 Jun 15 02:46 dev
drwxr-xr-x 2 root root 4096 Jun 15 02:46 etc
drwxr-xr-x 2 root root 4096 Jun 15 02:46 home
drwxr-xr-x 3 root root 4096 Jun 15 02:46 lib
drwxr-xr-x 2 root root 4096 Jun 15 02:46 lib64
drwxr-xr-x 3 root root 4096 Jun 15 02:46 usr
```
```bash
for package in $(ldd /bin/bash | awk '{print $(NF -1)}'); do cp $package /var/chroot/$package; done
cp: cannot stat 'linux-vdso.so.1': No such file or directory
```
```bash
echo $$
2030
```
```bash
chroot /var/chroot
```
```bash
echo $$
2190
```
```bash
uptime 
bash: uptime: command not found
```
```bash
ping -c 1 www.google.com
```
```bash
PING www.google.com (142.251.167.104) 56(84) bytes of data.
64 bytes from www.google.com (142.251.167.104): icmp_seq=1 ttl=105 time=19.3 ms

--- www.google.com ping statistics ---
1 packets transmitted, 1 received, 0% packet loss, time 0ms
rtt min/avg/max/mdev = 19.261/19.261/19.261/0.000 ms
```

```bash
chroot /var/chroot
```
```bash
curl www.google.com
```
```html
<!doctype html><html itemscope="" itemtype="http://schema.org/WebPage" lang="en"><head>...
```
```bash
cat /var/chroot/etc/hosts
127.0.0.1 localhost

# The following lines are desirable for IPv6 capable hosts
::1 ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
ff02::3 ip6-allhosts
127.0.0.1 ubuntu
127.0.0.1 host01
142.251.167.104 www.google.com google.com
```
```bash
cat /etc/hosts 
127.0.0.1 localhost

# The following lines are desirable for IPv6 capable hosts
::1 ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
ff02::3 ip6-allhosts
127.0.0.1 ubuntu
127.0.0.1 host01
142.251.167.104 www.google.com google.com
```
- If you were to write out the high level steps of building a chroot jail, what would they be?
    
- Think about what you did in the lab and what extra (or less) you might give a user/process.
    
    - What directories are needed?
    - What executables might you give the jailed user/process?
    - If you give an executable, why is it important to give the link libraries that it uses?
    - What are the special files that you made with mknod and why must they be there? (try removing them or redoing the lab without them. How does it break?)



```bash
ssh node01
Last login: Mon Feb 10 22:06:42 2025 from 10.244.0.131
node01:~$ mkdir /var/chroot
node01:~$ mkdir -p /var/chroot/{bin,lib64,dev,etc,home,usr/bin,lib/x86_64-linux-gnu}
node01:~$ ls -l /var/chroot
total 28
drwxr-xr-x 2 root root 4096 Jun 15 02:59 bin
drwxr-xr-x 2 root root 4096 Jun 15 02:59 dev
drwxr-xr-x 2 root root 4096 Jun 15 02:59 etc
drwxr-xr-x 2 root root 4096 Jun 15 02:59 home
drwxr-xr-x 3 root root 4096 Jun 15 02:59 lib
drwxr-xr-x 2 root root 4096 Jun 15 02:59 lib64
drwxr-xr-x 3 root root 4096 Jun 15 02:59 usr
node01:~$ cp /usr/bin/bash /var/chroot/bin/bash
node01:~$ for package in $(ldd /bin/bash | awk '{print $(NF -1)}'); do cp $package /var/chroot/$package; done
cp: cannot stat 'linux-vdso.so.1': No such file or directory
node01:~$ for file in passwd group nsswitch.conf hosts; do cp /etc/$file /var/chroot/etc/$file; done
node01:~$ for binary in bash ssh curl; do cp /usr/bin/$binary /var/chroot/usr/bin/$binary; done
node01:~$ ldd /usr/bin/bash
        linux-vdso.so.1 (0x00007ffcf8dac000)
        libtinfo.so.6 => /lib/x86_64-linux-gnu/libtinfo.so.6 (0x00007e100a4fe000)
        libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007e100a200000)
        /lib64/ld-linux-x86-64.so.2 (0x00007e100a6a7000)
node01:~$ for package in $(ldd /usr/bin/ssh | awk '{print $(NF -1)}'); do cp $package /var/chroot/$package; done
cp: cannot stat 'linux-vdso.so.1': No such file or directory
node01:~$ for package in $(ldd /usr/bin/curl | awk '{print $(NF -1)}'); do cp $package /var/chroot/$package; done
cp: cannot stat 'linux-vdso.so.1': No such file or directory
node01:~$ mknod -m 666 /var/chroot/dev/null c 1 3
node01:~$ mknod -m 666 /var/chroot/dev/null c 1 3
mknod: /var/chroot/dev/null: File exists
node01:~$ mknod -m 666 /var/chroot/dev/tty c 5 0
node01:~$ mknod -m 666 /var/chroot/dev/zero c 1 5
node01:~$ mknod -m 666 /var/chroot/dev/random c 1 8
node01:~$ mknod -m 666 /var/chroot/dev/urandom c 1 9
node01:~$ cp -r /lib/x86_64-linux-gnu/*nss* /var/chroot/lib/x86_64-linux-gnu/
node01:~$ exit
logout
Connection to node01 closed.
```

```bash
hostname
controlplane
controlplane:~$ ssh jaileduser@node01
jaileduser@node01's password: 
Make your selection from the items below
You have 20 seconds

1. Connect to controlplane as freeuser.
2. Exit
1
You are being sent to Rocky1
The authenticity of host 'controlplane (172.30.1.2)' can't be established.
ED25519 key fingerprint is SHA256:XikjTSvie4xfSHl8CD14UKeq6b3m5zuJAlVVC6JLlao.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/jaileduser/.ssh' (No such file or directory).
Failed to add the host to the list of known hosts (/home/jaileduser/.ssh/known_hosts).
freeuser@controlplane's password: 
$ id
uid=1001(freeuser) gid=1001(freeuser) groups=1001(freeuser)
$ hostname
controlplane
```


```bash
ssh jaileduser@node01
jaileduser@node01's password: 
Last login: Sun Jun 15 03:03:16 2025 from 10.244.7.112
Make your selection from the items below
You have 20 seconds

1. Connect to controlplane as freeuser.
2. Exit
You have not entered a valid input
Connection to node01 closed.
```

- If you were to write out the high level steps of building a bastion host, what would they be?
    
- When you jump into the bastion host, do you have any options other than the one you have given yourself?
    
- How did you test that you couldn't leave the jailed environment?
    
    - How effective do you think this is as a technical preventative control against user breakout in the jail, having a 20 second timeout?

