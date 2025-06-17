
*apt -y install gnutls-bin rsyslog-gnutls

```
echo "Installing scenario..."
while [ ! -f /tmp/finished ]; do sleep 1; done
echo DONE
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libevent-2.1-7t64 libgnutls-dane0t64 libgnutls30t64 libunbound8 rsyslog
Suggested packages:
  rsyslog-mysql | rsyslog-pgsql rsyslog-mongodb rsyslog-doc rsyslog-gssapi rsyslog-relp
The following NEW packages will be installed:
  gnutls-bin libevent-2.1-7t64 libgnutls-dane0t64 libunbound8 rsyslog-gnutls
The following packages will be upgraded:
  libgnutls30t64 rsyslog
2 upgraded, 5 newly installed, 0 to remove and 142 not upgraded.
Need to get 2406 kB of archives.
After this operation, 2748 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libgnutls30t64 amd64 3.8.3-1.1ubuntu3.3 [995 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 rsyslog amd64 8.2312.0-3ubuntu9.1 [511 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble/main amd64 libevent-2.1-7t64 amd64 2.1.12-stable-9ubuntu2 [145 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libunbound8 amd64 1.19.2-1ubuntu3.4 [442 kB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libgnutls-dane0t64 amd64 3.8.3-1.1ubuntu3.3 [23.5 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 gnutls-bin amd64 3.8.3-1.1ubuntu3.3 [270 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 rsyslog-gnutls amd64 8.2312.0-3ubuntu9.1 [19.9 kB]
Fetched 2406 kB in 1s (2614 kB/s)          
(Reading database ... 140010 files and directories currently installed.)
Preparing to unpack .../libgnutls30t64_3.8.3-1.1ubuntu3.3_amd64.deb ...
Unpacking libgnutls30t64:amd64 (3.8.3-1.1ubuntu3.3) over (3.8.3-1.1ubuntu3.2) ...
Setting up libgnutls30t64:amd64 (3.8.3-1.1ubuntu3.3) ...
(Reading database ... 140010 files and directories currently installed.)
Preparing to unpack .../0-rsyslog_8.2312.0-3ubuntu9.1_amd64.deb ...
Unpacking rsyslog (8.2312.0-3ubuntu9.1) over (8.2312.0-3ubuntu9) ...
Selecting previously unselected package libevent-2.1-7t64:amd64.
Preparing to unpack .../1-libevent-2.1-7t64_2.1.12-stable-9ubuntu2_amd64.deb ...
Unpacking libevent-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Selecting previously unselected package libunbound8:amd64.
Preparing to unpack .../2-libunbound8_1.19.2-1ubuntu3.4_amd64.deb ...
Unpacking libunbound8:amd64 (1.19.2-1ubuntu3.4) ...
Selecting previously unselected package libgnutls-dane0t64:amd64.
Preparing to unpack .../3-libgnutls-dane0t64_3.8.3-1.1ubuntu3.3_amd64.deb ...
Unpacking libgnutls-dane0t64:amd64 (3.8.3-1.1ubuntu3.3) ...
Selecting previously unselected package gnutls-bin.
Preparing to unpack .../4-gnutls-bin_3.8.3-1.1ubuntu3.3_amd64.deb ...
Unpacking gnutls-bin (3.8.3-1.1ubuntu3.3) ...
Selecting previously unselected package rsyslog-gnutls.
Preparing to unpack .../5-rsyslog-gnutls_8.2312.0-3ubuntu9.1_amd64.deb ...
Unpacking rsyslog-gnutls (8.2312.0-3ubuntu9.1) ...
Setting up rsyslog (8.2312.0-3ubuntu9.1) ...
Installing new version of config file /etc/apparmor.d/usr.sbin.rsyslogd ...
info: The user `syslog' is already a member of `adm'.
Setting up libevent-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Setting up rsyslog-gnutls (8.2312.0-3ubuntu9.1) ...
Setting up libunbound8:amd64 (1.19.2-1ubuntu3.4) ...
Setting up libgnutls-dane0t64:amd64 (3.8.3-1.1ubuntu3.3) ...
Setting up gnutls-bin (3.8.3-1.1ubuntu3.3) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
Scanning processes...                                                                                                                                                                      
Scanning candidates...                                                                                                                                                                     
Scanning linux images...                                                                                                                                                                   

Running kernel seems to be up-to-date.

Restarting services...
 systemctl restart cups-browsed.service cups.service fwupd.service

Service restarts being deferred:
 systemctl restart NetworkManager.service

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
```


*ssh node01 'apt -y install gnutls-bin rsyslog-gnutls'


```
WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

Reading package lists...
Building dependency tree...
Reading state information...
The following package was automatically installed and is no longer required:
  squashfs-tools
Use 'apt autoremove' to remove it.
The following additional packages will be installed:
  libevent-2.1-7t64 libgnutls-dane0t64 libgnutls30t64 libunbound8 rsyslog
Suggested packages:
  rsyslog-mysql | rsyslog-pgsql rsyslog-mongodb rsyslog-doc rsyslog-gssapi
  rsyslog-relp
The following NEW packages will be installed:
  gnutls-bin libevent-2.1-7t64 libgnutls-dane0t64 libunbound8 rsyslog-gnutls
The following packages will be upgraded:
  libgnutls30t64 rsyslog
2 upgraded, 5 newly installed, 0 to remove and 160 not upgraded.
Need to get 2406 kB of archives.
After this operation, 2748 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libgnutls30t64 amd64 3.8.3-1.1ubuntu3.3 [995 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 rsyslog amd64 8.2312.0-3ubuntu9.1 [511 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble/main amd64 libevent-2.1-7t64 amd64 2.1.12-stable-9ubuntu2 [145 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libunbound8 amd64 1.19.2-1ubuntu3.4 [442 kB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libgnutls-dane0t64 amd64 3.8.3-1.1ubuntu3.3 [23.5 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 gnutls-bin amd64 3.8.3-1.1ubuntu3.3 [270 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 rsyslog-gnutls amd64 8.2312.0-3ubuntu9.1 [19.9 kB]
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (This frontend requires a controlling tty.)
debconf: falling back to frontend: Teletype
dpkg-preconfigure: unable to re-open stdin: 
Fetched 2406 kB in 1s (2583 kB/s)
(Reading database ... 82216 files and directories currently installed.)
Preparing to unpack .../libgnutls30t64_3.8.3-1.1ubuntu3.3_amd64.deb ...
Unpacking libgnutls30t64:amd64 (3.8.3-1.1ubuntu3.3) over (3.8.3-1.1ubuntu3.2) ...
Setting up libgnutls30t64:amd64 (3.8.3-1.1ubuntu3.3) ...
(Reading database ... 82216 files and directories currently installed.)
Preparing to unpack .../0-rsyslog_8.2312.0-3ubuntu9.1_amd64.deb ...
Unpacking rsyslog (8.2312.0-3ubuntu9.1) over (8.2312.0-3ubuntu9) ...
Selecting previously unselected package libevent-2.1-7t64:amd64.
Preparing to unpack .../1-libevent-2.1-7t64_2.1.12-stable-9ubuntu2_amd64.deb ...
Unpacking libevent-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Selecting previously unselected package libunbound8:amd64.
Preparing to unpack .../2-libunbound8_1.19.2-1ubuntu3.4_amd64.deb ...
Unpacking libunbound8:amd64 (1.19.2-1ubuntu3.4) ...
Selecting previously unselected package libgnutls-dane0t64:amd64.
Preparing to unpack .../3-libgnutls-dane0t64_3.8.3-1.1ubuntu3.3_amd64.deb ...
Unpacking libgnutls-dane0t64:amd64 (3.8.3-1.1ubuntu3.3) ...
Selecting previously unselected package gnutls-bin.
Preparing to unpack .../4-gnutls-bin_3.8.3-1.1ubuntu3.3_amd64.deb ...
Unpacking gnutls-bin (3.8.3-1.1ubuntu3.3) ...
Selecting previously unselected package rsyslog-gnutls.
Preparing to unpack .../5-rsyslog-gnutls_8.2312.0-3ubuntu9.1_amd64.deb ...
Unpacking rsyslog-gnutls (8.2312.0-3ubuntu9.1) ...
Setting up rsyslog (8.2312.0-3ubuntu9.1) ...
Installing new version of config file /etc/apparmor.d/usr.sbin.rsyslogd ...
info: The user `syslog' is already a member of `adm'.
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (This frontend requires a controlling tty.)
debconf: falling back to frontend: Teletype
Setting up libevent-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Setting up rsyslog-gnutls (8.2312.0-3ubuntu9.1) ...
Setting up libunbound8:amd64 (1.19.2-1ubuntu3.4) ...
Setting up libgnutls-dane0t64:amd64 (3.8.3-1.1ubuntu3.3) ...
Setting up gnutls-bin (3.8.3-1.1ubuntu3.3) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (This frontend requires a controlling tty.)
debconf: falling back to frontend: Teletype

Running kernel seems to be up-to-date.

Restarting services...
 systemctl restart fwupd.service

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host
```


*certtool --generate-privkey --outfile ca-key.pem

```
Generating a 3072 bit RSA private key...
```


*certtool --generate-self-signed --load-privkey ca-key.pem --outfile ca.pem

```
Generating a self signed certificate...
Please enter the details of the certificate's distinguished name. Just press enter to ignore a field.
Country name (2 chars): certtool --generate-self-signed --load-privkey ca-key.pem --outfile ca.pem
State or province name: 
Locality name: 
Organization name: ProLUG
Organizational unit name: 
Common name: 
UID: 
Enter the subject's domain component (DC): 
This field should not be used in new certificates.
E-mail: 
Enter the certificate's serial number in decimal (123) or hex (0xabcd)
(default is 0x36033b6c5f159d16851b09d908eecc28b824e745)
value: 


*Activation/Expiration time.
The certificate will expire in (days): 90


*Extensions.
Does the certificate belong to an authority? (y/N): 
Is this a TLS web client certificate? (y/N): 
Will the certificate be used for IPsec IKE operations? (y/N): 
Is this a TLS web server certificate? (y/N): 
Enter a dnsName of the subject of the certificate: 
Enter a URI of the subject of the certificate: 
Enter the IP address of the subject of the certificate: 
Enter the e-mail of the subject of the certificate: 
Will the certificate be used for signing (required for TLS)? (Y/n): 
Will the certificate be used for encryption (not required for TLS)? (Y/n): 
Will the certificate be used for data encryption? (y/N): 
Will the certificate be used to sign OCSP requests? (y/N): 
Will the certificate be used to sign code? (y/N): 
Will the certificate be used for time stamping? (y/N): 
Will the certificate be used for email protection? (y/N): 
Enter the URI of the CRL distribution point: 
X.509 Certificate Information:
        Version: 3
        Serial Number (hex): 36033b6c5f159d16851b09d908eecc28b824e745
        Validity:
                Not Before: Sat Jun 14 04:25:32 UTC 2025
                Not After: Fri Sep 12 04:25:38 UTC 2025
        Subject: O=ProLUG,C=certtool --generate-self-signed --load-privkey ca-key.pem --outfile ca.pem
        Subject Public Key Algorithm: RSA
        Algorithm Security Level: High (3072 bits)
                Modulus (bits 3072):
                        00:c7:77:e0:83:6f:5c:f3:1e:b2:b7:e5:d9:dd:ef:63
                        ec:f8:b7:ba:1e:bd:93:64:95:eb:ad:eb:3c:24:5d:df
                        fd:03:49:1b:f4:8d:c1:c7:84:ad:cd:82:5c:72:c3:25
                        da:de:9d:dc:9a:1f:ff:9a:ce:c4:c7:4f:a6:aa:23:40
                        90:ab:80:3c:1c:b8:92:b6:c0:9f:10:14:fd:d8:04:84
                        ef:54:c0:49:0c:ae:de:e2:70:0c:f1:8d:2b:5e:23:c6
                        b7:b6:f8:b9:f8:02:b3:58:0d:8f:a2:11:2b:f1:7d:04
                        f9:4c:5b:c2:69:9b:20:39:56:65:c0:57:38:ca:9b:ce
                        91:cf:75:90:a1:c7:7c:9b:9a:3e:bc:85:f4:b5:f0:dd
                        4a:f9:74:8b:dd:6a:6f:2b:9a:75:c5:98:0b:ed:39:ab
                        87:76:97:f3:77:95:4d:b3:a3:f3:01:8b:7d:a0:c0:50
                        6f:94:85:8a:12:57:80:bd:9a:5d:08:2e:d7:1c:7d:43
                        d1:e9:25:87:8f:9b:27:22:df:bf:f6:fc:bc:40:c2:a4
                        e6:fe:9f:ff:f5:85:47:eb:12:c3:49:0d:b5:80:76:75
                        9d:63:a6:e7:48:5e:10:08:81:07:e3:b9:40:44:ae:36
                        15:6f:09:1b:f3:72:0f:d2:42:2d:9f:80:c2:3a:b6:2f
                        aa:92:3b:94:ea:a7:94:6d:9b:f5:3b:ca:cd:80:40:d2
                        4b:78:ca:58:b4:1b:f5:20:a3:1d:75:a7:a4:1b:1e:d0
                        6b:a4:64:63:bf:a4:75:85:47:c3:77:e1:d5:b1:a6:f5
                        12:d4:01:01:d1:22:ba:68:2b:86:53:b7:2f:4c:86:86
                        32:49:c2:36:2f:85:5a:82:ae:ab:ac:2e:c3:1e:8a:56
                        55:5b:fa:16:0a:e6:64:5c:a1:f9:a4:9a:93:b8:b2:d9
                        f0:46:67:dc:c7:2d:a9:91:26:9b:1b:c3:9d:a4:95:8c
                        35:42:42:91:15:c6:16:26:cd:7f:1c:95:c8:21:a7:21
                        b5
                Exponent (bits 24):
                        01:00:01
        Extensions:
                Basic Constraints (critical):
                        Certificate Authority (CA): FALSE
                Key Usage (critical):
                        Digital signature.
                        Key encipherment.
                Subject Key Identifier (not critical):
                        ffbecb48f54147519dbb0fb6d39316ed6293fa7e
Other Information:
        Public Key ID:
                sha1:ffbecb48f54147519dbb0fb6d39316ed6293fa7e
                sha256:4d467ce40da3a6aac494b255ad59172633287ac2962c06f72993d611a4dcc8d8
        Public Key PIN:
                pin-sha256:TUZ85A2jpqrElLJVrVkXJjMoesKWLAb3KZPWEaTcyNg=

Is the above information ok? (y/N): y


Signing certificate...
```


*ls -l*

```
total 12
-rw------- 1 root root 8177 Jun 14 04:23 ca-key.pem
-rw-r--r-- 1 root root 1655 Jun 14 04:26 ca.pem
```

*certtool --generate-privkey --outfile key.pem

```
Generating a 3072 bit RSA private key...
```


*certtool --generate-request --load-privkey key.pem --outfile request.pem*

```
Generating a PKCS #10 certificate request...
Country name (2 chars): certtool --generate-request --load-privkey key.pem --outfile request.pem
State or province name: 
Locality name: 
Organization name: 
Organizational unit name: 
Common name: 
UID: 
Enter the subject's domain component (DC): 
Enter a dnsName of the subject of the certificate: 
Enter a URI of the subject of the certificate: 
Enter the IP address of the subject of the certificate: 
Enter the e-mail of the subject of the certificate: 
Enter a challenge password: 
Does the certificate belong to an authority? (y/N): 
Will the certificate be used for signing (DHE ciphersuites)? (Y/n): 
Will the certificate be used for encryption (RSA ciphersuites)? (Y/n): 
Will the certificate be used to sign code? (y/N): 
Will the certificate be used for time stamping? (y/N): 
Will the certificate be used for email protection? (y/N): 
Will the certificate be used for IPsec IKE operations? (y/N): 
Will the certificate be used to sign OCSP requests? (y/N): 
Is this a TLS web client certificate? (y/N): 
Is this a TLS web server certificate? (y/N): 
```

*certtool --generate-certificate --load-request request.pem --outfile cert.pem --load-ca-certificate ca.pem --load-ca-privkey ca-key.pem
```
Generating a signed certificate...
Enter the certificate's serial number in decimal (123) or hex (0xabcd)
(default is 0x700626f1e13c3548059f56723436f10699a89100)
value: 


Activation/Expiration time.
The certificate will expire in (days): 60


Extensions.
Do you want to honour all the extensions from the request? (y/N): 
Does the certificate belong to an authority? (y/N): 
Is this a TLS web client certificate? (y/N): y
Will the certificate be used for IPsec IKE operations? (y/N): 
Is this a TLS web server certificate? (y/N): 
Enter a dnsName of the subject of the certificate: controlplane
Enter an additional dnsName of the subject of the certificate: 
Enter a URI of the subject of the certificate: 
Enter the IP address of the subject of the certificate: 
Enter the e-mail of the subject of the certificate: 
Will the certificate be used for signing (required for TLS)? (Y/n): 
Will the certificate be used for encryption (not required for TLS)? (Y/n): 
Will the certificate be used for data encryption? (y/N): 
Will the certificate be used to sign OCSP requests? (y/N): 
Will the certificate be used to sign code? (y/N): 
Will the certificate be used for time stamping? (y/N): 
Will the certificate be used for email protection? (y/N): 
Enter the URI of the CRL distribution point: 
X.509 Certificate Information:
        Version: 3
        Serial Number (hex): 700626f1e13c3548059f56723436f10699a89100
        Validity:
                Not Before: Sat Jun 14 04:34:48 UTC 2025
                Not After: Wed Aug 13 04:34:52 UTC 2025
        Subject: C=certtool --generate-request --load-privkey key.pem --outfile request.pem
        Subject Public Key Algorithm: RSA
        Algorithm Security Level: High (3072 bits)
                Modulus (bits 3072):
                        00:c9:6c:94:48:a8:f3:39:44:fc:38:16:dd:33:0c:d7
                        15:6b:2d:e0:98:69:02:d3:66:b1:d9:6a:30:c2:42:f5
                        9c:3b:b8:fa:76:76:b1:0f:cc:fb:41:2d:98:89:aa:cf
                        fb:4b:6f:13:5b:34:0b:70:a8:c8:4c:b4:7c:aa:0d:67
                        1c:c2:b7:87:66:65:dc:9e:7d:1d:9f:45:ae:3f:87:25
                        29:2c:83:97:77:a6:16:9f:1d:f7:86:67:e0:2d:d3:47
                        5a:2d:cf:a1:e9:73:f7:5b:a6:ce:4c:f6:bf:81:4c:fd
                        de:a0:4c:3c:50:b3:7c:87:e6:0d:a2:bd:fb:bf:ad:c1
                        53:28:e0:fb:07:00:17:ba:f4:35:a4:59:ee:4c:44:81
                        96:e4:1b:9e:6f:e5:07:8e:4b:9d:31:5f:29:16:53:5c
                        6b:39:1c:d2:e7:79:a9:d1:98:25:cb:ec:9f:65:d9:95
                        5d:70:a0:c0:4c:d0:08:a0:b6:94:1a:c8:70:b5:7f:6b
                        ed:e6:90:f7:b9:e8:3c:7c:70:b3:4a:a8:54:c3:16:91
                        6c:51:03:5f:72:26:db:32:e4:ce:37:f6:1d:69:38:5e
                        57:69:5b:9f:15:4a:ba:0e:2f:f2:ef:eb:65:ff:17:d4
                        11:54:bc:50:38:75:a6:20:2f:19:35:c3:c4:c3:92:fb
                        5a:4e:90:ae:00:60:c5:1e:87:7d:4e:e4:d8:ff:6b:53
                        b0:19:da:01:99:7d:c3:4a:21:6f:96:fd:90:de:07:be
                        1d:c1:19:b0:4a:36:73:d3:ae:60:f8:84:41:f4:5a:ed
                        98:3f:58:16:83:52:88:83:c4:33:46:0a:c3:84:05:b3
                        89:b3:3a:7d:44:94:e6:5e:bd:e1:34:cd:f6:28:fb:b9
                        b9:32:95:ec:a3:5f:55:9f:d2:f7:2c:d1:56:ea:76:f5
                        6b:0d:7d:57:fb:d3:6a:0c:4c:6c:af:ef:bf:f2:46:f6
                        c5:39:ef:be:e7:72:e2:e4:fa:16:b9:20:78:7c:37:ec
                        7b
                Exponent (bits 24):
                        01:00:01
        Extensions:
                Basic Constraints (critical):
                        Certificate Authority (CA): FALSE
                Key Purpose (not critical):
                        TLS WWW Client.
                Subject Alternative Name (not critical):
                        DNSname: controlplane
                Key Usage (critical):
                        Digital signature.
                        Key encipherment.
                Subject Key Identifier (not critical):
                        1cb2a55fa647a877f6bc0351bb485921875ecb26
                Authority Key Identifier (not critical):
                        ffbecb48f54147519dbb0fb6d39316ed6293fa7e
Other Information:
        Public Key ID:
                sha1:1cb2a55fa647a877f6bc0351bb485921875ecb26
                sha256:86abe055e8b4d5794d0fc276e10b60e9cafae3d82525c0ba02a50e8333a8b06c
        Public Key PIN:
                pin-sha256:hqvgVei01XlND8J24Qtg6cr649glJcC6AqUOgzOosGw=

Is the above information ok? (y/N): y


Signing certificate...

```
*certtool --certificate-info --infile cert.pem | grep -i control
```
DNSname: controlplane
```
*chown root:syslog /usr/local/share/ca-certificates/key.pem 
chmod 640 /usr/local/share/ca-certificates/key.pem
ls -l
```

total 28
-rw------- 1 root root   8177 Jun 14 04:23 ca-key.pem
-rw-r--r-- 1 root root   1655 Jun 14 04:26 ca.pem
-rw-r--r-- 1 root root   1740 Jun 14 04:35 cert.pem
-rw-r----- 1 root syslog 8177 Jun 14 04:32 key.pem
-rw------- 1 root root   3360 Jun 14 04:33 request.pem

```
*scp /usr/local/share/ca-certificates/ca.pem node01:/usr/local/share/ca-certificates/ca.pem 
ca.pem



*status rsyslog --no-pager
```
● rsyslog.service - System Logging Service
     Loaded: loaded (/usr/lib/systemd/system/rsyslog.service; enabled; preset: enabled)
     Active: active (running) since Sat 2025-06-14 04:42:54 UTC; 3s ago
TriggeredBy: ● syslog.socket
       Docs: man:rsyslogd(8)
             man:rsyslog.conf(5)
             https://www.rsyslog.com/doc/
    Process: 76963 ExecStartPre=/usr/lib/rsyslog/reload-apparmor-profile (code=exited, status=0/SUCCESS)
   Main PID: 76969 (rsyslogd)
      Tasks: 9 (limit: 2614)
     Memory: 2.0M (peak: 5.0M)
        CPU: 218ms
     CGroup: /system.slice/rsyslog.service
             └─76969 /usr/sbin/rsyslogd -n -iNONE

Jun 14 04:42:54 controlplane systemd[1]: Starting rsyslog.service - System Logging Service...
Jun 14 04:42:54 controlplane systemd[1]: Started rsyslog.service - System Logging Service.
Jun 14 04:42:54 controlplane rsyslogd[76969]: imuxsock: Acquired UNIX socket '/run/systemd/journal/syslog' (fd 3) from systemd.  [v8.2312.0]
Jun 14 04:42:54 controlplane rsyslogd[76969]: rsyslogd's groupid changed to 102
Jun 14 04:42:54 controlplane rsyslogd[76969]: rsyslogd's userid changed to 102
Jun 14 04:42:54 controlplane rsyslogd[76969]: [origin software="rsyslogd" swVersion="8.2312.0" x-pid="76969" x-info="https://www.rsyslog.com"] start

```
*ss -ntulp | grep 6514
```
tcp   LISTEN 0      25    0.0.0.0:6514       0.0.0.0:*    users:(("rsyslogd",pid=76969,fd=6))
tcp   LISTEN 0      25         [::]:6514          [::]:*              users:(("rsyslogd",pid=76969,fd=7))

```
*systemctl restart rsyslog
useradd -m someuser



*grep someuser /var/log/*

```
grep: /var/log/apt: Is a directory
grep: /var/log/auth.log: binary file matches
grep: /var/log/calico: Is a directory
grep: /var/log/containers: Is a directory
grep: /var/log/cups: Is a directory
grep: /var/log/cups-browsed: Is a directory
grep: /var/log/dist-upgrade: Is a directory
grep: /var/log/journal: Is a directory
grep: /var/log/killercoda: Is a directory
grep: /var/log/landscape: Is a directory
grep: /var/log/lightdm: Is a directory
grep: /var/log/pods: Is a directory
grep: /var/log/private: Is a directory
grep: /var/log/sysstat: Is a directory
grep: /var/log/unattended-upgrades: Is a directory

```
*ssh-keygen
```
Generating public/private ed25519 key pair.
Enter file in which to save the key (/root/.ssh/id_ed25519): ProLUG
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in ProLUG
Your public key has been saved in ProLUG.pub
The key fingerprint is:
SHA256:hIDkELvXZyNPbjSPfoZYa0qSgeFh1Uiwwt4EfS0hnMk root@controlplane
The key's randomart image is:
+--[ED25519 256]--+
|o=B=*.o          |
|.+=E.= o         |
|+=... o .        |
|=++.   .         |
|ooo.o B S        |
| . o O.=         |
|  o .o=o.        |
|   o.o+ o        |
|    .o.o         |
+----[SHA256]-----+

```
*ls -l 
```
total 8
-rw------- 1 root root 411 Jun 14 06:36 ProLUG
-rw-r--r-- 1 root root  99 Jun 14 06:36 ProLUG.
```

*ssh-keygen -y -e -f ProLUG
```
---- BEGIN SSH2 PUBLIC KEY ----
Comment: "256-bit ED25519, converted by root@controlplane from OpenSSH"
AAAAC3NzaC1lZDI1NTE5AAAAIKotozlLmT30djx05YdKzFosJ7pKRGLySSQP8axyZNtL
---- END SSH2 PUBLIC KEY ----
```
ssh-keygen -l -f ProLUG
```
256 SHA256:hIDkELvXZyNPbjSPfoZYa0qSgeFh1Uiwwt4EfS0hnMk root@controlplane (ED25519)
```
ssh-keygen -y -e -f ProLUG.pub
```
---- BEGIN SSH2 PUBLIC KEY ----
Comment: "256-bit ED25519, converted by root@controlplane from OpenSSH"
AAAAC3NzaC1lZDI1NTE5AAAAIKotozlLmT30djx05YdKzFosJ7pKRGLySSQP8axyZNtL
---- END SSH2 PUBLIC KEY ----
```
ssh-keygen -l -f ProLUG.pub
```
256 SHA256:hIDkELvXZyNPbjSPfoZYa0qSgeFh1Uiwwt4EfS0hnMk root@controlplane (ED25519)
```
rm -rf /root/keys/ProLUG.pub

*ls -l 
```
total 4
-rw------- 1 root root 411 Jun 14 06:36 ProLUG
```
ssh-keygen -f ProLUG -y > ProLUG.pub


*ssh node01
useradd -m prolug
passwd prolug
```
New password: 
Retype new password: 
passwd: password updated successfully
```
ssh-copy-id -i ProLUG prolug@node01
```
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "ProLUG.pub"
ssh-copy-id -i ProLUG prolug@node01
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
prolug@node01's password:
Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'prolug@node01'"
and check to make sure that only the key(s) you wanted were added.
```
*ssh -i ProLUG prolug@node01

*ls -ld /home/prolug/.ssh
```
drwx------ 2 prolug prolug 4096 Jun 14 06:43 /home/prolug/.ssh
```
cd /home/prolug/.ssh
ls -l
```
total 4
-rw------- 1 prolug prolug 99 Jun 14 06:43 authorized_keys
```
cat authorized_keys
```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIKotozlLmT30djx05YdKzFosJ7pKRGLySSQP8axyZNtL root@controlplane
```
ssh -v -i ProLUG prolug@node01
```
OpenSSH_9.6p1 Ubuntu-3ubuntu13.5, OpenSSL 3.0.13 30 Jan 2024
debug1: Reading configuration data /etc/ssh/ssh_config
debug1: /etc/ssh/ssh_config line 19: include /etc/ssh/ssh_config.d/*.conf matched no files
*debug1: /etc/ssh/ssh_config line 21: Applying options for *
debug1: Connecting to node01 [172.30.2.2] port 22.
debug1: Connection established.
debug1: identity file ProLUG type 3
debug1: identity file ProLUG-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_9.6p1 Ubuntu-3ubuntu13.5
debug1: Remote protocol version 2.0, remote software version OpenSSH_9.6p1 Ubuntu-3ubuntu13.5
debug1: compat_banner: match: OpenSSH_9.6p1 Ubuntu-3ubuntu13.5 pat OpenSSH* compat *0x04000000
debug1: Authenticating to node01:22 as 'prolug'
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: SSH2_MSG_KEXINIT sent
debug1: SSH2_MSG_KEXINIT received
debug1: kex: algorithm: sntrup761x25519-sha512@openssh.com
debug1: kex: host key algorithm: ssh-ed25519
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug1: SSH2_MSG_KEX_ECDH_REPLY received
debug1: Server host key: ssh-ed25519 SHA256:XikjTSvie4xfSHl8CD14UKeq6b3m5zuJAlVVC6JLlao
debug1: load_hostkeys: fopen /root/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: Host 'node01' is known and matches the ED25519 host key.
debug1: Found key in /root/.ssh/known_hosts:5
debug1: ssh_packet_send2_wrapped: resetting send seqnr 3
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: Sending SSH2_MSG_EXT_INFO
debug1: expecting SSH2_MSG_NEWKEYS
debug1: ssh_packet_read_poll2: resetting read seqnr 3
debug1: SSH2_MSG_NEWKEYS received
debug1: rekey in after 134217728 blocks
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_ext_info_client_parse: server-sig-algs=<ssh-ed25519,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ssh-ed25519@openssh.com,sk-ecdsa-sha2-nistp256@openssh.com,rsa-sha2-512,rsa-sha2-256>
debug1: kex_ext_info_check_ver: publickey-hostbound@openssh.com=<0>
debug1: kex_ext_info_check_ver: ping@openssh.com=<0>
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_ext_info_client_parse: server-sig-algs=<ssh-ed25519,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ssh-ed25519@openssh.com,sk-ecdsa-sha2-nistp256@openssh.com,rsa-sha2-512,rsa-sha2-256>
debug1: Authentications that can continue: publickey,password,keyboard-interactive
debug1: Next authentication method: publickey
debug1: Will attempt key: ProLUG ED25519 SHA256:hIDkELvXZyNPbjSPfoZYa0qSgeFh1Uiwwt4EfS0hnMk explicit
debug1: Offering public key: ProLUG ED25519 SHA256:hIDkELvXZyNPbjSPfoZYa0qSgeFh1Uiwwt4EfS0hnMk explicit
debug1: Server accepts key: ProLUG ED25519 SHA256:hIDkELvXZyNPbjSPfoZYa0qSgeFh1Uiwwt4EfS0hnMk explicit
Authenticated to node01 ([172.30.2.2]:22) using "publickey".
debug1: channel 0: new session [client-session] (inactive timeout: 0)
debug1: Requesting no-more-sessions@openssh.com
debug1: Entering interactive session.
debug1: pledge: filesystem
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts for node01 / (none)
debug1: client_input_hostkeys: searching /root/.ssh/known_hosts2 for node01 / (none)
debug1: client_input_hostkeys: hostkeys file /root/.ssh/known_hosts2 does not exist
debug1: client_input_hostkeys: host key found matching a different name/address, skipping UserKnownHostsFile update
debug1: Remote: /home/prolug/.ssh/authorized_keys:1: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Remote: /home/prolug/.ssh/authorized_keys:1: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
debug1: Sending environment.
debug1: pledge: fork
Last login: Sat Jun 14 06:44:28 2025 from 10.244.8.22
```

