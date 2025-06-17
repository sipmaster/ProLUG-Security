*mount | grep -i noexec
```bash
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
cgroup2 on /sys/fs/cgroup type cgroup2 (rw,nosuid,nodev,noexec,relatime,seclabel,nsdelegate,memory_recursiveprot)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime,seclabel)
bpf on /sys/fs/bpf type bpf (rw,nosuid,nodev,noexec,relatime,mode=700)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,nosuid,noexec,relatime)
debugfs on /sys/kernel/debug type debugfs (rw,nosuid,nodev,noexec,relatime,seclabel)
tracefs on /sys/kernel/tracing type tracefs (rw,nosuid,nodev,noexec,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime,seclabel)
fusectl on /sys/fs/fuse/connections type fusectl (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysctl.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
configfs on /sys/kernel/config type configfs (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysusers.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup-dev.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
```
*mount | grep -i nodev*
```bash
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel,inode64)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,size=793760k,nr_inodes=819200,mode=755,inode64)
cgroup2 on /sys/fs/cgroup type cgroup2 (rw,nosuid,nodev,noexec,relatime,seclabel,nsdelegate,memory_recursiveprot)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime,seclabel)
bpf on /sys/fs/bpf type bpf (rw,nosuid,nodev,noexec,relatime,mode=700)
debugfs on /sys/kernel/debug type debugfs (rw,nosuid,nodev,noexec,relatime,seclabel)
tracefs on /sys/kernel/tracing type tracefs (rw,nosuid,nodev,noexec,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime,seclabel)
fusectl on /sys/fs/fuse/connections type fusectl (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysctl.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
configfs on /sys/kernel/config type configfs (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysusers.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup-dev.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=396876k,nr_inodes=99219,mode=700,inode64)

```
*mount | grep -i nosuid*
```bash
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=4096k,nr_inodes=487279,mode=755,inode64)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel,inode64)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,size=793760k,nr_inodes=819200,mode=755,inode64)
cgroup2 on /sys/fs/cgroup type cgroup2 (rw,nosuid,nodev,noexec,relatime,seclabel,nsdelegate,memory_recursiveprot)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime,seclabel)
bpf on /sys/fs/bpf type bpf (rw,nosuid,nodev,noexec,relatime,mode=700)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,nosuid,noexec,relatime)
debugfs on /sys/kernel/debug type debugfs (rw,nosuid,nodev,noexec,relatime,seclabel)
tracefs on /sys/kernel/tracing type tracefs (rw,nosuid,nodev,noexec,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime,seclabel)
fusectl on /sys/fs/fuse/connections type fusectl (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysctl.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
configfs on /sys/kernel/config type configfs (rw,nosuid,nodev,noexec,relatime)
none on /run/credentials/systemd-sysusers.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup-dev.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
none on /run/credentials/systemd-tmpfiles-setup.service type ramfs (ro,nosuid,nodev,noexec,relatime,seclabel,mode=700)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=396876k,nr_inodes=99219,mode=700,inode64)

```
 
 Approximately how many of your mounted filesystems have each of these values?

*sysctl -a | grep -i ipv4*

```bash
net.ipv4.cipso_cache_bucket_size = 10
net.ipv4.cipso_cache_enable = 1
net.ipv4.cipso_rbm_optfmt = 0
net.ipv4.cipso_rbm_strictvalid = 1
net.ipv4.conf.all.accept_local = 0
net.ipv4.conf.all.accept_redirects = 0
net.ipv4.conf.all.accept_source_route = 0
net.ipv4.conf.all.arp_accept = 0
net.ipv4.conf.all.arp_announce = 0
net.ipv4.conf.all.arp_filter = 0
net.ipv4.conf.all.arp_ignore = 0
net.ipv4.conf.all.arp_notify = 0
net.ipv4.conf.all.bc_forwarding = 0
net.ipv4.conf.all.bootp_relay = 0
net.ipv4.conf.all.disable_policy = 0
net.ipv4.conf.all.disable_xfrm = 0
net.ipv4.conf.all.drop_gratuitous_arp = 0
net.ipv4.conf.all.drop_unicast_in_l2_multicast = 0
net.ipv4.conf.all.force_igmp_version = 0
net.ipv4.conf.all.forwarding = 0
net.ipv4.conf.all.igmpv2_unsolicited_report_interval = 10000
net.ipv4.conf.all.igmpv3_unsolicited_report_interval = 1000
net.ipv4.conf.all.ignore_routes_with_linkdown = 0
net.ipv4.conf.all.log_martians = 0
net.ipv4.conf.all.mc_forwarding = 0
net.ipv4.conf.all.medium_id = 0
net.ipv4.conf.all.promote_secondaries = 0
net.ipv4.conf.all.proxy_arp = 0
net.ipv4.conf.all.proxy_arp_pvlan = 0
net.ipv4.conf.all.route_localnet = 0
net.ipv4.conf.all.rp_filter = 1
net.ipv4.conf.all.secure_redirects = 1
net.ipv4.conf.all.send_redirects = 0
net.ipv4.conf.all.shared_media = 1
net.ipv4.conf.all.src_valid_mark = 0
net.ipv4.conf.all.tag = 0
net.ipv4.conf.default.accept_local = 0
net.ipv4.conf.default.accept_redirects = 0
net.ipv4.conf.default.accept_source_route = 0
net.ipv4.conf.default.arp_accept = 0
net.ipv4.conf.default.arp_announce = 0
net.ipv4.conf.default.arp_filter = 0
net.ipv4.conf.default.arp_ignore = 0
net.ipv4.conf.default.arp_notify = 0
net.ipv4.conf.default.bc_forwarding = 0
net.ipv4.conf.default.bootp_relay = 0
net.ipv4.conf.default.disable_policy = 0
net.ipv4.conf.default.disable_xfrm = 0
net.ipv4.conf.default.drop_gratuitous_arp = 0
net.ipv4.conf.default.drop_unicast_in_l2_multicast = 0
net.ipv4.conf.default.force_igmp_version = 0
net.ipv4.conf.default.forwarding = 0
net.ipv4.conf.default.igmpv2_unsolicited_report_interval = 10000
net.ipv4.conf.default.igmpv3_unsolicited_report_interval = 1000
net.ipv4.conf.default.ignore_routes_with_linkdown = 0
net.ipv4.conf.default.log_martians = 0
net.ipv4.conf.default.mc_forwarding = 0
net.ipv4.conf.default.medium_id = 0
net.ipv4.conf.default.promote_secondaries = 1
net.ipv4.conf.default.proxy_arp = 0
net.ipv4.conf.default.proxy_arp_pvlan = 0
net.ipv4.conf.default.route_localnet = 0
net.ipv4.conf.default.rp_filter = 1
net.ipv4.conf.default.secure_redirects = 1
net.ipv4.conf.default.send_redirects = 0
net.ipv4.conf.default.shared_media = 1
net.ipv4.conf.default.src_valid_mark = 0
net.ipv4.conf.default.tag = 0
net.ipv4.conf.eth0.accept_local = 0
net.ipv4.conf.eth0.accept_redirects = 1
net.ipv4.conf.eth0.accept_source_route = 0
net.ipv4.conf.eth0.arp_accept = 0
net.ipv4.conf.eth0.arp_announce = 0
net.ipv4.conf.eth0.arp_filter = 0
net.ipv4.conf.eth0.arp_ignore = 0
net.ipv4.conf.eth0.arp_notify = 0
net.ipv4.conf.eth0.bc_forwarding = 0
net.ipv4.conf.eth0.bootp_relay = 0
net.ipv4.conf.eth0.disable_policy = 0
net.ipv4.conf.eth0.disable_xfrm = 0
net.ipv4.conf.eth0.drop_gratuitous_arp = 0
net.ipv4.conf.eth0.drop_unicast_in_l2_multicast = 0
net.ipv4.conf.eth0.force_igmp_version = 0
net.ipv4.conf.eth0.forwarding = 0
net.ipv4.conf.eth0.igmpv2_unsolicited_report_interval = 10000
net.ipv4.conf.eth0.igmpv3_unsolicited_report_interval = 1000
net.ipv4.conf.eth0.ignore_routes_with_linkdown = 0
net.ipv4.conf.eth0.log_martians = 0
net.ipv4.conf.eth0.mc_forwarding = 0
net.ipv4.conf.eth0.medium_id = 0
net.ipv4.conf.eth0.promote_secondaries = 1
net.ipv4.conf.eth0.proxy_arp = 0
net.ipv4.conf.eth0.proxy_arp_pvlan = 0
net.ipv4.conf.eth0.route_localnet = 0
net.ipv4.conf.eth0.rp_filter = 1
net.ipv4.conf.eth0.secure_redirects = 1
net.ipv4.conf.eth0.send_redirects = 1
net.ipv4.conf.eth0.shared_media = 1
net.ipv4.conf.eth0.src_valid_mark = 0
net.ipv4.conf.eth0.tag = 0
net.ipv4.conf.lo.accept_local = 0
net.ipv4.conf.lo.accept_redirects = 1
net.ipv4.conf.lo.accept_source_route = 0
net.ipv4.conf.lo.arp_accept = 0
net.ipv4.conf.lo.arp_announce = 0
net.ipv4.conf.lo.arp_filter = 0
net.ipv4.conf.lo.arp_ignore = 0
net.ipv4.conf.lo.arp_notify = 0
net.ipv4.conf.lo.bc_forwarding = 0
net.ipv4.conf.lo.bootp_relay = 0
net.ipv4.conf.lo.disable_policy = 1
net.ipv4.conf.lo.disable_xfrm = 1
net.ipv4.conf.lo.drop_gratuitous_arp = 0
net.ipv4.conf.lo.drop_unicast_in_l2_multicast = 0
net.ipv4.conf.lo.force_igmp_version = 0
net.ipv4.conf.lo.forwarding = 0
net.ipv4.conf.lo.igmpv2_unsolicited_report_interval = 10000
net.ipv4.conf.lo.igmpv3_unsolicited_report_interval = 1000
net.ipv4.conf.lo.ignore_routes_with_linkdown = 0
net.ipv4.conf.lo.log_martians = 0
net.ipv4.conf.lo.mc_forwarding = 0
net.ipv4.conf.lo.medium_id = 0
net.ipv4.conf.lo.promote_secondaries = 1
net.ipv4.conf.lo.proxy_arp = 0
net.ipv4.conf.lo.proxy_arp_pvlan = 0
net.ipv4.conf.lo.route_localnet = 0
net.ipv4.conf.lo.rp_filter = 1
net.ipv4.conf.lo.secure_redirects = 1
net.ipv4.conf.lo.send_redirects = 1
net.ipv4.conf.lo.shared_media = 1
net.ipv4.conf.lo.src_valid_mark = 0
net.ipv4.conf.lo.tag = 0
net.ipv4.fib_multipath_hash_fields = 7
net.ipv4.fib_multipath_hash_policy = 0
net.ipv4.fib_multipath_use_neigh = 0
net.ipv4.fib_notify_on_flag_change = 0
net.ipv4.fib_sync_mem = 524288
net.ipv4.fwmark_reflect = 0
net.ipv4.icmp_echo_enable_probe = 0
net.ipv4.icmp_echo_ignore_all = 0
net.ipv4.icmp_echo_ignore_broadcasts = 1
net.ipv4.icmp_errors_use_inbound_ifaddr = 0
net.ipv4.icmp_ignore_bogus_error_responses = 1
net.ipv4.icmp_msgs_burst = 50
net.ipv4.icmp_msgs_per_sec = 1000
net.ipv4.icmp_ratelimit = 1000
net.ipv4.icmp_ratemask = 6168
net.ipv4.igmp_link_local_mcast_reports = 1
net.ipv4.igmp_max_memberships = 20
net.ipv4.igmp_max_msf = 10
net.ipv4.igmp_qrv = 2
net.ipv4.inet_peer_maxttl = 600
net.ipv4.inet_peer_minttl = 120
net.ipv4.inet_peer_threshold = 65664
net.ipv4.ip_autobind_reuse = 0
net.ipv4.ip_default_ttl = 64
net.ipv4.ip_dynaddr = 0
net.ipv4.ip_early_demux = 1
net.ipv4.ip_forward = 0
net.ipv4.ip_forward_update_priority = 1
net.ipv4.ip_forward_use_pmtu = 0
net.ipv4.ip_local_port_range = 32768    60999
net.ipv4.ip_local_reserved_ports =
net.ipv4.ip_no_pmtu_disc = 0
net.ipv4.ip_nonlocal_bind = 0
net.ipv4.ip_unprivileged_port_start = 1024
net.ipv4.ipfrag_high_thresh = 4194304
net.ipv4.ipfrag_low_thresh = 3145728
net.ipv4.ipfrag_max_dist = 64
net.ipv4.ipfrag_secret_interval = 0
net.ipv4.ipfrag_time = 30
net.ipv4.neigh.default.anycast_delay = 100
net.ipv4.neigh.default.app_solicit = 0
net.ipv4.neigh.default.base_reachable_time_ms = 30000
net.ipv4.neigh.default.delay_first_probe_time = 5
net.ipv4.neigh.default.gc_interval = 30
net.ipv4.neigh.default.gc_stale_time = 60
net.ipv4.neigh.default.gc_thresh1 = 128
net.ipv4.neigh.default.gc_thresh2 = 512
net.ipv4.neigh.default.gc_thresh3 = 1024
net.ipv4.neigh.default.locktime = 100
net.ipv4.neigh.default.mcast_resolicit = 0
net.ipv4.neigh.default.mcast_solicit = 3
net.ipv4.neigh.default.proxy_delay = 80
net.ipv4.neigh.default.proxy_qlen = 64
net.ipv4.neigh.default.retrans_time_ms = 1000
net.ipv4.neigh.default.ucast_solicit = 3
net.ipv4.neigh.default.unres_qlen = 101
net.ipv4.neigh.default.unres_qlen_bytes = 212992
net.ipv4.neigh.eth0.anycast_delay = 100
net.ipv4.neigh.eth0.app_solicit = 0
net.ipv4.neigh.eth0.base_reachable_time_ms = 30000
net.ipv4.neigh.eth0.delay_first_probe_time = 5
net.ipv4.neigh.eth0.gc_stale_time = 60
net.ipv4.neigh.eth0.locktime = 100
net.ipv4.neigh.eth0.mcast_resolicit = 0
net.ipv4.neigh.eth0.mcast_solicit = 3
net.ipv4.neigh.eth0.proxy_delay = 80
net.ipv4.neigh.eth0.proxy_qlen = 64
net.ipv4.neigh.eth0.retrans_time_ms = 1000
net.ipv4.neigh.eth0.ucast_solicit = 3
net.ipv4.neigh.eth0.unres_qlen = 101
net.ipv4.neigh.eth0.unres_qlen_bytes = 212992
net.ipv4.neigh.lo.anycast_delay = 100
net.ipv4.neigh.lo.app_solicit = 0
net.ipv4.neigh.lo.base_reachable_time_ms = 30000
net.ipv4.neigh.lo.delay_first_probe_time = 5
net.ipv4.neigh.lo.gc_stale_time = 60
net.ipv4.neigh.lo.locktime = 100
net.ipv4.neigh.lo.mcast_resolicit = 0
net.ipv4.neigh.lo.mcast_solicit = 3
net.ipv4.neigh.lo.proxy_delay = 80
net.ipv4.neigh.lo.proxy_qlen = 64
net.ipv4.neigh.lo.retrans_time_ms = 1000
net.ipv4.neigh.lo.ucast_solicit = 3
net.ipv4.neigh.lo.unres_qlen = 101
net.ipv4.neigh.lo.unres_qlen_bytes = 212992
net.ipv4.nexthop_compat_mode = 1
net.ipv4.ping_group_range = 0   2147483647
net.ipv4.raw_l3mdev_accept = 1
net.ipv4.route.error_burst = 5000
net.ipv4.route.error_cost = 1000
net.ipv4.route.gc_elasticity = 8
net.ipv4.route.gc_interval = 60
net.ipv4.route.gc_min_interval = 0
net.ipv4.route.gc_min_interval_ms = 500
net.ipv4.route.gc_thresh = -1
net.ipv4.route.gc_timeout = 300
net.ipv4.route.max_size = 2147483647
net.ipv4.route.min_adv_mss = 256
net.ipv4.route.min_pmtu = 552
net.ipv4.route.mtu_expires = 600
net.ipv4.route.redirect_load = 20
net.ipv4.route.redirect_number = 9
net.ipv4.route.redirect_silence = 20480
net.ipv4.tcp_abort_on_overflow = 0
net.ipv4.tcp_adv_win_scale = 1
net.ipv4.tcp_allowed_congestion_control = reno cubic
net.ipv4.tcp_app_win = 31
net.ipv4.tcp_autocorking = 1
net.ipv4.tcp_available_congestion_control = reno cubic
net.ipv4.tcp_available_ulp = espintcp mptcp tls
net.ipv4.tcp_base_mss = 1024
net.ipv4.tcp_challenge_ack_limit = 1000
net.ipv4.tcp_comp_sack_delay_ns = 1000000
net.ipv4.tcp_comp_sack_nr = 44
net.ipv4.tcp_comp_sack_slack_ns = 100000
net.ipv4.tcp_congestion_control = cubic
net.ipv4.tcp_dsack = 1
net.ipv4.tcp_early_demux = 1
net.ipv4.tcp_early_retrans = 3
net.ipv4.tcp_ecn = 2
net.ipv4.tcp_ecn_fallback = 1
net.ipv4.tcp_fack = 0
net.ipv4.tcp_fastopen = 1
net.ipv4.tcp_fastopen_blackhole_timeout_sec = 0
net.ipv4.tcp_fastopen_key = 00000000-00000000-00000000-00000000
net.ipv4.tcp_fin_timeout = 60
net.ipv4.tcp_frto = 2
net.ipv4.tcp_fwmark_accept = 0
net.ipv4.tcp_invalid_ratelimit = 500
net.ipv4.tcp_keepalive_intvl = 75
net.ipv4.tcp_keepalive_probes = 9
net.ipv4.tcp_keepalive_time = 7200
net.ipv4.tcp_l3mdev_accept = 0
net.ipv4.tcp_limit_output_bytes = 1048576
net.ipv4.tcp_low_latency = 0
net.ipv4.tcp_max_orphans = 16384
net.ipv4.tcp_max_reordering = 300
net.ipv4.tcp_max_syn_backlog = 256
net.ipv4.tcp_max_tw_buckets = 16384
net.ipv4.tcp_mem = 44493        59326   88986
net.ipv4.tcp_migrate_req = 0
net.ipv4.tcp_min_rtt_wlen = 300
net.ipv4.tcp_min_snd_mss = 48
net.ipv4.tcp_min_tso_segs = 2
net.ipv4.tcp_moderate_rcvbuf = 1
net.ipv4.tcp_mtu_probe_floor = 48
net.ipv4.tcp_mtu_probing = 0
net.ipv4.tcp_no_metrics_save = 0
net.ipv4.tcp_no_ssthresh_metrics_save = 1
net.ipv4.tcp_notsent_lowat = 4294967295
net.ipv4.tcp_orphan_retries = 0
net.ipv4.tcp_pacing_ca_ratio = 120
net.ipv4.tcp_pacing_ss_ratio = 200
net.ipv4.tcp_probe_interval = 600
net.ipv4.tcp_probe_threshold = 8
net.ipv4.tcp_recovery = 1
net.ipv4.tcp_reflect_tos = 0
net.ipv4.tcp_reordering = 3
net.ipv4.tcp_retrans_collapse = 1
net.ipv4.tcp_retries1 = 3
net.ipv4.tcp_retries2 = 15
net.ipv4.tcp_rfc1337 = 0
net.ipv4.tcp_rmem = 4096        131072  6291456
net.ipv4.tcp_sack = 1
net.ipv4.tcp_shrink_window = 0
net.ipv4.tcp_slow_start_after_idle = 1
net.ipv4.tcp_stdurg = 0
net.ipv4.tcp_syn_retries = 6
net.ipv4.tcp_synack_retries = 5
net.ipv4.tcp_syncookies = 1
net.ipv4.tcp_thin_linear_timeouts = 0
net.ipv4.tcp_timestamps = 1
net.ipv4.tcp_tso_win_divisor = 3
net.ipv4.tcp_tw_reuse = 2
net.ipv4.tcp_window_scaling = 1
net.ipv4.tcp_wmem = 4096        16384   4194304
net.ipv4.tcp_workaround_signed_windows = 0
net.ipv4.udp_early_demux = 1
net.ipv4.udp_l3mdev_accept = 0
net.ipv4.udp_mem = 88989        118652  177978
net.ipv4.udp_rmem_min = 4096
net.ipv4.udp_wmem_min = 4096
net.ipv4.xfrm4_gc_thresh = 32768
```

*sysctl -a | grep -i ipv4 | wc -l*
```bash
315
```

*sysctl -a | grep -i ipv6*
```bash
net.ipv6.anycast_src_echo_reply = 0
net.ipv6.auto_flowlabels = 1
net.ipv6.bindv6only = 0
net.ipv6.calipso_cache_bucket_size = 10
net.ipv6.calipso_cache_enable = 1
net.ipv6.conf.all.accept_dad = 0
net.ipv6.conf.all.accept_ra = 0
net.ipv6.conf.all.accept_ra_defrtr = 1
net.ipv6.conf.all.accept_ra_from_local = 0
net.ipv6.conf.all.accept_ra_min_hop_limit = 1
net.ipv6.conf.all.accept_ra_mtu = 1
net.ipv6.conf.all.accept_ra_pinfo = 1
net.ipv6.conf.all.accept_ra_rt_info_max_plen = 0
net.ipv6.conf.all.accept_ra_rt_info_min_plen = 0
net.ipv6.conf.all.accept_ra_rtr_pref = 1
net.ipv6.conf.all.accept_redirects = 0
net.ipv6.conf.all.accept_source_route = 0
net.ipv6.conf.all.addr_gen_mode = 0
net.ipv6.conf.all.autoconf = 1
net.ipv6.conf.all.dad_transmits = 1
net.ipv6.conf.all.disable_ipv6 = 0
net.ipv6.conf.all.disable_policy = 0
net.ipv6.conf.all.drop_unicast_in_l2_multicast = 0
net.ipv6.conf.all.drop_unsolicited_na = 0
net.ipv6.conf.all.enhanced_dad = 1
net.ipv6.conf.all.force_mld_version = 0
net.ipv6.conf.all.force_tllao = 0
net.ipv6.conf.all.forwarding = 0
net.ipv6.conf.all.hop_limit = 64
net.ipv6.conf.all.ignore_routes_with_linkdown = 0
net.ipv6.conf.all.keep_addr_on_down = 0
net.ipv6.conf.all.max_addresses = 16
net.ipv6.conf.all.max_desync_factor = 600
net.ipv6.conf.all.mc_forwarding = 0
net.ipv6.conf.all.mldv1_unsolicited_report_interval = 10000
net.ipv6.conf.all.mldv2_unsolicited_report_interval = 1000
net.ipv6.conf.all.mtu = 1280
net.ipv6.conf.all.ndisc_notify = 0
net.ipv6.conf.all.ndisc_tclass = 0
net.ipv6.conf.all.optimistic_dad = 0
net.ipv6.conf.all.proxy_ndp = 0
net.ipv6.conf.all.ra_defrtr_metric = 1024
net.ipv6.conf.all.regen_max_retry = 3
net.ipv6.conf.all.router_probe_interval = 60
net.ipv6.conf.all.router_solicitation_delay = 1
net.ipv6.conf.all.router_solicitation_interval = 4
net.ipv6.conf.all.router_solicitation_max_interval = 3600
net.ipv6.conf.all.router_solicitations = -1
net.ipv6.conf.all.rpl_seg_enabled = 0
net.ipv6.conf.all.seg6_enabled = 0
net.ipv6.conf.all.seg6_require_hmac = 0
net.ipv6.conf.all.suppress_frag_ndisc = 1
net.ipv6.conf.all.temp_prefered_lft = 86400
net.ipv6.conf.all.temp_valid_lft = 604800
net.ipv6.conf.all.use_oif_addrs_only = 0
net.ipv6.conf.all.use_optimistic = 0
net.ipv6.conf.all.use_tempaddr = 0
net.ipv6.conf.default.accept_dad = 1
net.ipv6.conf.default.accept_ra = 0
net.ipv6.conf.default.accept_ra_defrtr = 1
net.ipv6.conf.default.accept_ra_from_local = 0
net.ipv6.conf.default.accept_ra_min_hop_limit = 1
net.ipv6.conf.default.accept_ra_mtu = 1
net.ipv6.conf.default.accept_ra_pinfo = 1
net.ipv6.conf.default.accept_ra_rt_info_max_plen = 0
net.ipv6.conf.default.accept_ra_rt_info_min_plen = 0
net.ipv6.conf.default.accept_ra_rtr_pref = 1
net.ipv6.conf.default.accept_redirects = 0
net.ipv6.conf.default.accept_source_route = 0
net.ipv6.conf.default.addr_gen_mode = 0
net.ipv6.conf.default.autoconf = 1
net.ipv6.conf.default.dad_transmits = 1
net.ipv6.conf.default.disable_ipv6 = 0
net.ipv6.conf.default.disable_policy = 0
net.ipv6.conf.default.drop_unicast_in_l2_multicast = 0
net.ipv6.conf.default.drop_unsolicited_na = 0
net.ipv6.conf.default.enhanced_dad = 1
net.ipv6.conf.default.force_mld_version = 0
net.ipv6.conf.default.force_tllao = 0
net.ipv6.conf.default.forwarding = 0
net.ipv6.conf.default.hop_limit = 64
net.ipv6.conf.default.ignore_routes_with_linkdown = 0
net.ipv6.conf.default.keep_addr_on_down = 0
net.ipv6.conf.default.max_addresses = 16
net.ipv6.conf.default.max_desync_factor = 600
net.ipv6.conf.default.mc_forwarding = 0
net.ipv6.conf.default.mldv1_unsolicited_report_interval = 10000
net.ipv6.conf.default.mldv2_unsolicited_report_interval = 1000
net.ipv6.conf.default.mtu = 1280
net.ipv6.conf.default.ndisc_notify = 0
net.ipv6.conf.default.ndisc_tclass = 0
net.ipv6.conf.default.optimistic_dad = 0
net.ipv6.conf.default.proxy_ndp = 0
net.ipv6.conf.default.ra_defrtr_metric = 1024
net.ipv6.conf.default.regen_max_retry = 3
net.ipv6.conf.default.router_probe_interval = 60
net.ipv6.conf.default.router_solicitation_delay = 1
net.ipv6.conf.default.router_solicitation_interval = 4
net.ipv6.conf.default.router_solicitation_max_interval = 3600
net.ipv6.conf.default.router_solicitations = -1
net.ipv6.conf.default.rpl_seg_enabled = 0
net.ipv6.conf.default.seg6_enabled = 0
net.ipv6.conf.default.seg6_require_hmac = 0
net.ipv6.conf.default.suppress_frag_ndisc = 1
net.ipv6.conf.default.temp_prefered_lft = 86400
net.ipv6.conf.default.temp_valid_lft = 604800
net.ipv6.conf.default.use_oif_addrs_only = 0
net.ipv6.conf.default.use_optimistic = 0
net.ipv6.conf.default.use_tempaddr = 0
net.ipv6.conf.eth0.accept_dad = 1
net.ipv6.conf.eth0.accept_ra = 0
net.ipv6.conf.eth0.accept_ra_defrtr = 1
net.ipv6.conf.eth0.accept_ra_from_local = 0
net.ipv6.conf.eth0.accept_ra_min_hop_limit = 1
net.ipv6.conf.eth0.accept_ra_mtu = 1
net.ipv6.conf.eth0.accept_ra_pinfo = 1
net.ipv6.conf.eth0.accept_ra_rt_info_max_plen = 0
net.ipv6.conf.eth0.accept_ra_rt_info_min_plen = 0
net.ipv6.conf.eth0.accept_ra_rtr_pref = 1
net.ipv6.conf.eth0.accept_redirects = 1
net.ipv6.conf.eth0.accept_source_route = 0
net.ipv6.conf.eth0.addr_gen_mode = 1
net.ipv6.conf.eth0.autoconf = 1
net.ipv6.conf.eth0.dad_transmits = 1
net.ipv6.conf.eth0.disable_ipv6 = 0
net.ipv6.conf.eth0.disable_policy = 0
net.ipv6.conf.eth0.drop_unicast_in_l2_multicast = 0
net.ipv6.conf.eth0.drop_unsolicited_na = 0
net.ipv6.conf.eth0.enhanced_dad = 1
net.ipv6.conf.eth0.force_mld_version = 0
net.ipv6.conf.eth0.force_tllao = 0
net.ipv6.conf.eth0.forwarding = 0
net.ipv6.conf.eth0.hop_limit = 64
net.ipv6.conf.eth0.ignore_routes_with_linkdown = 0
net.ipv6.conf.eth0.keep_addr_on_down = 0
net.ipv6.conf.eth0.max_addresses = 16
net.ipv6.conf.eth0.max_desync_factor = 600
net.ipv6.conf.eth0.mc_forwarding = 0
net.ipv6.conf.eth0.mldv1_unsolicited_report_interval = 10000
net.ipv6.conf.eth0.mldv2_unsolicited_report_interval = 1000
net.ipv6.conf.eth0.mtu = 1500
net.ipv6.conf.eth0.ndisc_notify = 0
net.ipv6.conf.eth0.ndisc_tclass = 0
net.ipv6.conf.eth0.optimistic_dad = 0
net.ipv6.conf.eth0.proxy_ndp = 0
net.ipv6.conf.eth0.ra_defrtr_metric = 1024
net.ipv6.conf.eth0.regen_max_retry = 3
net.ipv6.conf.eth0.router_probe_interval = 60
net.ipv6.conf.eth0.router_solicitation_delay = 1
net.ipv6.conf.eth0.router_solicitation_interval = 4
net.ipv6.conf.eth0.router_solicitation_max_interval = 3600
net.ipv6.conf.eth0.router_solicitations = -1
net.ipv6.conf.eth0.rpl_seg_enabled = 0
net.ipv6.conf.eth0.seg6_enabled = 0
net.ipv6.conf.eth0.seg6_require_hmac = 0
net.ipv6.conf.eth0.suppress_frag_ndisc = 1
net.ipv6.conf.eth0.temp_prefered_lft = 86400
net.ipv6.conf.eth0.temp_valid_lft = 604800
net.ipv6.conf.eth0.use_oif_addrs_only = 0
net.ipv6.conf.eth0.use_optimistic = 0
net.ipv6.conf.eth0.use_tempaddr = 0
net.ipv6.conf.lo.accept_dad = -1
net.ipv6.conf.lo.accept_ra = 1
net.ipv6.conf.lo.accept_ra_defrtr = 1
net.ipv6.conf.lo.accept_ra_from_local = 0
net.ipv6.conf.lo.accept_ra_min_hop_limit = 1
net.ipv6.conf.lo.accept_ra_mtu = 1
net.ipv6.conf.lo.accept_ra_pinfo = 1
net.ipv6.conf.lo.accept_ra_rt_info_max_plen = 0
net.ipv6.conf.lo.accept_ra_rt_info_min_plen = 0
net.ipv6.conf.lo.accept_ra_rtr_pref = 1
net.ipv6.conf.lo.accept_redirects = 1
net.ipv6.conf.lo.accept_source_route = 0
net.ipv6.conf.lo.addr_gen_mode = 0
net.ipv6.conf.lo.autoconf = 1
net.ipv6.conf.lo.dad_transmits = 1
net.ipv6.conf.lo.disable_ipv6 = 0
net.ipv6.conf.lo.disable_policy = 0
net.ipv6.conf.lo.drop_unicast_in_l2_multicast = 0
net.ipv6.conf.lo.drop_unsolicited_na = 0
net.ipv6.conf.lo.enhanced_dad = 1
net.ipv6.conf.lo.force_mld_version = 0
net.ipv6.conf.lo.force_tllao = 0
net.ipv6.conf.lo.forwarding = 0
net.ipv6.conf.lo.hop_limit = 64
net.ipv6.conf.lo.ignore_routes_with_linkdown = 0
net.ipv6.conf.lo.keep_addr_on_down = 0
net.ipv6.conf.lo.max_addresses = 16
net.ipv6.conf.lo.max_desync_factor = 600
net.ipv6.conf.lo.mc_forwarding = 0
net.ipv6.conf.lo.mldv1_unsolicited_report_interval = 10000
net.ipv6.conf.lo.mldv2_unsolicited_report_interval = 1000
net.ipv6.conf.lo.mtu = 65536
net.ipv6.conf.lo.ndisc_notify = 0
net.ipv6.conf.lo.ndisc_tclass = 0
net.ipv6.conf.lo.optimistic_dad = 0
net.ipv6.conf.lo.proxy_ndp = 0
net.ipv6.conf.lo.ra_defrtr_metric = 1024
net.ipv6.conf.lo.regen_max_retry = 3
net.ipv6.conf.lo.router_probe_interval = 60
net.ipv6.conf.lo.router_solicitation_delay = 1
net.ipv6.conf.lo.router_solicitation_interval = 4
net.ipv6.conf.lo.router_solicitation_max_interval = 3600
net.ipv6.conf.lo.router_solicitations = -1
net.ipv6.conf.lo.rpl_seg_enabled = 0
net.ipv6.conf.lo.seg6_enabled = 0
net.ipv6.conf.lo.seg6_require_hmac = 0
net.ipv6.conf.lo.suppress_frag_ndisc = 1
net.ipv6.conf.lo.temp_prefered_lft = 86400
net.ipv6.conf.lo.temp_valid_lft = 604800
net.ipv6.conf.lo.use_oif_addrs_only = 0
net.ipv6.conf.lo.use_optimistic = 0
net.ipv6.conf.lo.use_tempaddr = -1
net.ipv6.fib_multipath_hash_fields = 7
net.ipv6.fib_multipath_hash_policy = 0
net.ipv6.fib_notify_on_flag_change = 0
net.ipv6.flowlabel_consistency = 1
net.ipv6.flowlabel_reflect = 0
net.ipv6.flowlabel_state_ranges = 0
net.ipv6.fwmark_reflect = 0
net.ipv6.icmp.echo_ignore_all = 0
net.ipv6.icmp.echo_ignore_anycast = 0
net.ipv6.icmp.echo_ignore_multicast = 0
net.ipv6.icmp.ratelimit = 1000
net.ipv6.icmp.ratemask = 0-1,3-127
net.ipv6.idgen_delay = 1
net.ipv6.idgen_retries = 3
net.ipv6.ip6frag_high_thresh = 4194304
net.ipv6.ip6frag_low_thresh = 3145728
net.ipv6.ip6frag_secret_interval = 0
net.ipv6.ip6frag_time = 60
net.ipv6.ip_nonlocal_bind = 0
net.ipv6.max_dst_opts_length = 2147483647
net.ipv6.max_dst_opts_number = 8
net.ipv6.max_hbh_length = 2147483647
net.ipv6.max_hbh_opts_number = 8
net.ipv6.mld_max_msf = 64
net.ipv6.mld_qrv = 2
net.ipv6.neigh.default.anycast_delay = 100
net.ipv6.neigh.default.app_solicit = 0
net.ipv6.neigh.default.base_reachable_time_ms = 30000
net.ipv6.neigh.default.delay_first_probe_time = 5
net.ipv6.neigh.default.gc_interval = 30
net.ipv6.neigh.default.gc_stale_time = 60
net.ipv6.neigh.default.gc_thresh1 = 128
net.ipv6.neigh.default.gc_thresh2 = 512
net.ipv6.neigh.default.gc_thresh3 = 1024
net.ipv6.neigh.default.locktime = 0
net.ipv6.neigh.default.mcast_resolicit = 0
net.ipv6.neigh.default.mcast_solicit = 3
net.ipv6.neigh.default.proxy_delay = 80
net.ipv6.neigh.default.proxy_qlen = 64
net.ipv6.neigh.default.retrans_time_ms = 1000
net.ipv6.neigh.default.ucast_solicit = 3
net.ipv6.neigh.default.unres_qlen = 101
net.ipv6.neigh.default.unres_qlen_bytes = 212992
net.ipv6.neigh.eth0.anycast_delay = 100
net.ipv6.neigh.eth0.app_solicit = 0
net.ipv6.neigh.eth0.base_reachable_time_ms = 30000
net.ipv6.neigh.eth0.delay_first_probe_time = 5
net.ipv6.neigh.eth0.gc_stale_time = 60
net.ipv6.neigh.eth0.locktime = 0
net.ipv6.neigh.eth0.mcast_resolicit = 0
net.ipv6.neigh.eth0.mcast_solicit = 3
net.ipv6.neigh.eth0.proxy_delay = 80
net.ipv6.neigh.eth0.proxy_qlen = 64
net.ipv6.neigh.eth0.retrans_time_ms = 1000
net.ipv6.neigh.eth0.ucast_solicit = 3
net.ipv6.neigh.eth0.unres_qlen = 101
net.ipv6.neigh.eth0.unres_qlen_bytes = 212992
net.ipv6.neigh.lo.anycast_delay = 100
net.ipv6.neigh.lo.app_solicit = 0
net.ipv6.neigh.lo.base_reachable_time_ms = 30000
net.ipv6.neigh.lo.delay_first_probe_time = 5
net.ipv6.neigh.lo.gc_stale_time = 60
net.ipv6.neigh.lo.locktime = 0
net.ipv6.neigh.lo.mcast_resolicit = 0
net.ipv6.neigh.lo.mcast_solicit = 3
net.ipv6.neigh.lo.proxy_delay = 80
net.ipv6.neigh.lo.proxy_qlen = 64
net.ipv6.neigh.lo.retrans_time_ms = 1000
net.ipv6.neigh.lo.ucast_solicit = 3
net.ipv6.neigh.lo.unres_qlen = 101
net.ipv6.neigh.lo.unres_qlen_bytes = 212992
net.ipv6.route.gc_elasticity = 9
net.ipv6.route.gc_interval = 30
net.ipv6.route.gc_min_interval = 0
net.ipv6.route.gc_min_interval_ms = 500
net.ipv6.route.gc_thresh = 1024
net.ipv6.route.gc_timeout = 60
net.ipv6.route.max_size = 2147483647
net.ipv6.route.min_adv_mss = 1220
net.ipv6.route.mtu_expires = 600
net.ipv6.route.skip_notify_on_dev_down = 0
net.ipv6.seg6_flowlabel = 0
net.ipv6.xfrm6_gc_thresh = 32768
```

*sysctl -a | grep -i ipv6 | wc -l*
```bash
296
```

*sysctl -a | grep -i ipv4 | grep -i forward*
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

*lsmod | grep -i tables*
```bash
nf_tables             356352  189 nft_ct,nft_reject_inet,nft_fib_ipv6,nft_fib_ipv4,nft_chain_nat,nft_reject,nft_fib,nft_fib_inet
libcrc32c              16384  3 nf_conntrack,nf_nat,nf_tables
nfnetlink              20480  3 nf_tables,ip_set
```

*dnf install mariadb-server*
```bash
Last metadata expiration check: 0:29:36 ago on Sat Jun 14 12:54:33 2025.
Dependencies resolved.
==============================================================================================================================================================================================================
 Package                                                     Architecture                            Version                                                 Repository                                  Size
==============================================================================================================================================================================================================
Installing:
 mariadb-server                                              x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                  9.7 M
Upgrading:
 selinux-policy                                              noarch                                  38.1.53-5.el9_6                                         baseos                                      44 k
 selinux-policy-devel                                        noarch                                  38.1.53-5.el9_6                                         appstream                                  1.2 M
 selinux-policy-targeted                                     noarch                                  38.1.53-5.el9_6                                         baseos                                     6.5 M
Installing dependencies:
 mariadb                                                     x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                  1.6 M
 mariadb-common                                              x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                   27 k
 mariadb-connector-c                                         x86_64                                  3.2.6-1.el9_0                                           appstream                                  195 k
 mariadb-connector-c-config                                  noarch                                  3.2.6-1.el9_0                                           appstream                                  9.8 k
 mariadb-errmsg                                              x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                  211 k
 mysql-selinux                                               noarch                                  1.0.13-1.el9_5                                          appstream                                   36 k
 perl-DBD-MariaDB                                            x86_64                                  1.21-16.el9_0                                           appstream                                  151 k
 perl-DBI                                                    x86_64                                  1.643-9.el9                                             appstream                                  700 k
 perl-DynaLoader                                             x86_64                                  1.47-481.el9                                            appstream                                   24 k
 perl-File-Copy                                              noarch                                  2.34-481.el9                                            appstream                                   19 k
 perl-Math-BigInt                                            noarch                                  1:1.9998.18-460.el9                                     appstream                                  188 k
 perl-Math-Complex                                           noarch                                  1.59-481.el9                                            appstream                                   45 k
 perl-Sys-Hostname                                           x86_64                                  1.23-481.el9                                            appstream                                   16 k
Installing weak dependencies:
 mariadb-backup                                              x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                  6.5 M
 mariadb-gssapi-server                                       x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                   14 k
 mariadb-server-utils                                        x86_64                                  3:10.5.27-1.el9_5.0.2                                   appstream                                  210 k

Transaction Summary
==============================================================================================================================================================================================================
Install  17 Packages
Upgrade   3 Packages

Total download size: 27 M
Is this ok [y/N]: y
Downloading Packages:
(1/20): mariadb-common-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                          44 kB/s |  27 kB     00:00
(2/20): mariadb-connector-c-3.2.6-1.el9_0.x86_64.rpm                                                                                                                          203 kB/s | 195 kB     00:00
(3/20): perl-DBI-1.643-9.el9.x86_64.rpm                                                                                                                                       691 kB/s | 700 kB     00:01
(4/20): mariadb-server-utils-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                   513 kB/s | 210 kB     00:00
(5/20): mariadb-connector-c-config-3.2.6-1.el9_0.noarch.rpm                                                                                                                   101 kB/s | 9.8 kB     00:00
(6/20): perl-Math-Complex-1.59-481.el9.noarch.rpm                                                                                                                             264 kB/s |  45 kB     00:00
(7/20): perl-Sys-Hostname-1.23-481.el9.x86_64.rpm                                                                                                                              71 kB/s |  16 kB     00:00
(8/20): perl-File-Copy-2.34-481.el9.noarch.rpm                                                                                                                                109 kB/s |  19 kB     00:00
(9/20): mariadb-backup-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                          13 MB/s | 6.5 MB     00:00
(10/20): mysql-selinux-1.0.13-1.el9_5.noarch.rpm                                                                                                                              142 kB/s |  36 kB     00:00
(11/20): perl-DynaLoader-1.47-481.el9.x86_64.rpm                                                                                                                               79 kB/s |  24 kB     00:00
(12/20): mariadb-server-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                        9.7 MB/s | 9.7 MB     00:00
(13/20): perl-Math-BigInt-1.9998.18-460.el9.noarch.rpm                                                                                                                        206 kB/s | 188 kB     00:00
(14/20): perl-DBD-MariaDB-1.21-16.el9_0.x86_64.rpm                                                                                                                            757 kB/s | 151 kB     00:00
(15/20): mariadb-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                               4.3 MB/s | 1.6 MB     00:00
(16/20): mariadb-gssapi-server-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                  37 kB/s |  14 kB     00:00
(17/20): mariadb-errmsg-10.5.27-1.el9_5.0.2.x86_64.rpm                                                                                                                        509 kB/s | 211 kB     00:00
(18/20): selinux-policy-38.1.53-5.el9_6.noarch.rpm                                                                                                                            195 kB/s |  44 kB     00:00
(19/20): selinux-policy-devel-38.1.53-5.el9_6.noarch.rpm                                                                                                                      3.8 MB/s | 1.2 MB     00:00
(20/20): selinux-policy-targeted-38.1.53-5.el9_6.noarch.rpm                                                                                                                   8.6 MB/s | 6.5 MB     00:00
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                         6.9 MB/s |  27 MB     00:03
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Running scriptlet: selinux-policy-targeted-38.1.53-5.el9_6.noarch                                                                                                                                       1/1
  Preparing        :                                                                                                                                                                                      1/1
  Upgrading        : selinux-policy-38.1.53-5.el9_6.noarch                                                                                                                                               1/23
  Running scriptlet: selinux-policy-38.1.53-5.el9_6.noarch                                                                                                                                               1/23
  Running scriptlet: selinux-policy-targeted-38.1.53-5.el9_6.noarch                                                                                                                                      2/23
  Upgrading        : selinux-policy-targeted-38.1.53-5.el9_6.noarch                                                                                                                                      2/23
  Running scriptlet: selinux-policy-targeted-38.1.53-5.el9_6.noarch                                                                                                                                      2/23
  Installing       : mariadb-connector-c-config-3.2.6-1.el9_0.noarch                                                                                                                                     3/23
  Installing       : mariadb-common-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                         4/23
  Installing       : mariadb-connector-c-3.2.6-1.el9_0.x86_64                                                                                                                                            5/23
  Installing       : perl-DynaLoader-1.47-481.el9.x86_64                                                                                                                                                 6/23
  Installing       : perl-Sys-Hostname-1.23-481.el9.x86_64                                                                                                                                               7/23
  Installing       : mariadb-errmsg-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                         8/23
  Running scriptlet: mysql-selinux-1.0.13-1.el9_5.noarch                                                                                                                                                 9/23
  Installing       : mysql-selinux-1.0.13-1.el9_5.noarch                                                                                                                                                 9/23
  Running scriptlet: mysql-selinux-1.0.13-1.el9_5.noarch                                                                                                                                                 9/23
libsemanage.semanage_direct_install_info: Overriding mysql module at lower priority 100 with module at priority 200.

  Installing       : perl-File-Copy-2.34-481.el9.noarch                                                                                                                                                 10/23
  Installing       : perl-Math-Complex-1.59-481.el9.noarch                                                                                                                                              11/23
  Installing       : perl-Math-BigInt-1:1.9998.18-460.el9.noarch                                                                                                                                        12/23
  Installing       : perl-DBI-1.643-9.el9.x86_64                                                                                                                                                        13/23
  Installing       : perl-DBD-MariaDB-1.21-16.el9_0.x86_64                                                                                                                                              14/23
  Installing       : mariadb-server-utils-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                  15/23
  Installing       : mariadb-backup-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                        16/23
  Installing       : mariadb-gssapi-server-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                 17/23
  Running scriptlet: mariadb-server-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                        18/23
  Installing       : mariadb-server-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                        18/23
  Running scriptlet: mariadb-server-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                        18/23
  Installing       : mariadb-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                               19/23
  Upgrading        : selinux-policy-devel-38.1.53-5.el9_6.noarch                                                                                                                                        20/23
  Running scriptlet: selinux-policy-devel-38.1.53-5.el9_6.noarch                                                                                                                                        20/23
  Cleanup          : selinux-policy-devel-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                                  21/23
  Running scriptlet: selinux-policy-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                                        22/23
  Cleanup          : selinux-policy-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                                        22/23
  Running scriptlet: selinux-policy-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                                        22/23
  Cleanup          : selinux-policy-targeted-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                               23/23
  Running scriptlet: selinux-policy-targeted-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                               23/23
  Running scriptlet: selinux-policy-targeted-38.1.53-5.el9_6.noarch                                                                                                                                     23/23
  Running scriptlet: mysql-selinux-1.0.13-1.el9_5.noarch                                                                                                                                                23/23
  Running scriptlet: selinux-policy-targeted-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                               23/23
  Verifying        : mariadb-connector-c-3.2.6-1.el9_0.x86_64                                                                                                                                            1/23
  Verifying        : mariadb-common-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                         2/23
  Verifying        : perl-DBI-1.643-9.el9.x86_64                                                                                                                                                         3/23
  Verifying        : mariadb-server-utils-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                   4/23
  Verifying        : mariadb-connector-c-config-3.2.6-1.el9_0.noarch                                                                                                                                     5/23
  Verifying        : mariadb-backup-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                         6/23
  Verifying        : perl-Math-Complex-1.59-481.el9.noarch                                                                                                                                               7/23
  Verifying        : perl-Sys-Hostname-1.23-481.el9.x86_64                                                                                                                                               8/23
  Verifying        : perl-File-Copy-2.34-481.el9.noarch                                                                                                                                                  9/23
  Verifying        : mariadb-server-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                        10/23
  Verifying        : perl-Math-BigInt-1:1.9998.18-460.el9.noarch                                                                                                                                        11/23
  Verifying        : mysql-selinux-1.0.13-1.el9_5.noarch                                                                                                                                                12/23
  Verifying        : perl-DynaLoader-1.47-481.el9.x86_64                                                                                                                                                13/23
  Verifying        : perl-DBD-MariaDB-1.21-16.el9_0.x86_64                                                                                                                                              14/23
  Verifying        : mariadb-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                               15/23
  Verifying        : mariadb-gssapi-server-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                 16/23
  Verifying        : mariadb-errmsg-3:10.5.27-1.el9_5.0.2.x86_64                                                                                                                                        17/23
  Verifying        : selinux-policy-38.1.53-5.el9_6.noarch                                                                                                                                              18/23
  Verifying        : selinux-policy-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                                        19/23
  Verifying        : selinux-policy-targeted-38.1.53-5.el9_6.noarch                                                                                                                                     20/23
  Verifying        : selinux-policy-targeted-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                               21/23
  Verifying        : selinux-policy-devel-38.1.53-5.el9_6.noarch                                                                                                                                        22/23
  Verifying        : selinux-policy-devel-38.1.35-2.el9_4.2.0.2.noarch                                                                                                                                  23/23

Upgraded:
  selinux-policy-38.1.53-5.el9_6.noarch                          selinux-policy-devel-38.1.53-5.el9_6.noarch                          selinux-policy-targeted-38.1.53-5.el9_6.noarch
Installed:
  mariadb-3:10.5.27-1.el9_5.0.2.x86_64                  mariadb-backup-3:10.5.27-1.el9_5.0.2.x86_64     mariadb-common-3:10.5.27-1.el9_5.0.2.x86_64            mariadb-connector-c-3.2.6-1.el9_0.x86_64
  mariadb-connector-c-config-3.2.6-1.el9_0.noarch       mariadb-errmsg-3:10.5.27-1.el9_5.0.2.x86_64     mariadb-gssapi-server-3:10.5.27-1.el9_5.0.2.x86_64     mariadb-server-3:10.5.27-1.el9_5.0.2.x86_64
  mariadb-server-utils-3:10.5.27-1.el9_5.0.2.x86_64     mysql-selinux-1.0.13-1.el9_5.noarch             perl-DBD-MariaDB-1.21-16.el9_0.x86_64                  perl-DBI-1.643-9.el9.x86_64
  perl-DynaLoader-1.47-481.el9.x86_64                   perl-File-Copy-2.34-481.el9.noarch              perl-Math-BigInt-1:1.9998.18-460.el9.noarch            perl-Math-Complex-1.59-481.el9.noarch
  perl-Sys-Hostname-1.23-481.el9.x86_64

Complete!

```

*systemctl start mariadb*

*systemctl status mariadb*
```bash
● mariadb.service - MariaDB 10.5 database server
     Loaded: loaded (/usr/lib/systemd/system/mariadb.service; disabled; preset: disabled)
     Active: active (running) since Sat 2025-06-14 13:26:14 MST; 57s ago
       Docs: man:mariadbd(8)
             https://mariadb.com/kb/en/library/systemd/
    Process: 21641 ExecStartPre=/usr/libexec/mariadb-check-socket (code=exited, status=0/SUCCESS)
    Process: 21663 ExecStartPre=/usr/libexec/mariadb-prepare-db-dir mariadb.service (code=exited, status=0/SUCCESS)
    Process: 21764 ExecStartPost=/usr/libexec/mariadb-check-upgrade (code=exited, status=0/SUCCESS)
   Main PID: 21747 (mariadbd)
     Status: "Taking your SQL requests now..."
      Tasks: 15 (limit: 24363)
     Memory: 192.6M
        CPU: 1.136s
     CGroup: /system.slice/mariadb.service
             └─21747 /usr/libexec/mariadbd --basedir=/usr

Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: The second is mysql@localhost, it has no password either, but
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: you need to be the system 'mysql' user to connect.
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: After connecting you can set the password, if you would need to be
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: able to connect as any of these users with a password and without sudo
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: See the MariaDB Knowledgebase at https://mariadb.com/kb
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: Please report any problems at https://mariadb.org/jira
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: The latest information about MariaDB is available at https://mariadb.org/.
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: Consider joining MariaDB's strong and vibrant community:
Jun 14 13:26:14 hammer10 mariadb-prepare-db-dir[21702]: https://mariadb.org/get-involved/
Jun 14 13:26:14 hammer10 systemd[1]: Started MariaDB 10.5 database server.
```

*ss -ntulp | grep 3306*
```bash
tcp   LISTEN 0      80                 *:3306            *:*    users:(("mariadbd",pid=21747,fd=19))
```


![[Pasted image 20250614163847.png]]

- What is the problem
```
MariaDB must limit the number of concurrent sessions to an organization-defined number per user for all accounts and/or account types.
```
- What is the fix? 
```
-To limit the number of connections allowed by a specific user, as a user with appropriate privileges, run the following SQL:

MariaDB> GRANT USAGE ON *.* TO  'username'@'host'  WITH MAX_USER_CONNECTIONS number_of_connections;
```
- What type of control is being implemented?
- Is it set properly on your system?

*mysql*
```mysql
SELECT user, max_user_connections FROM mysql.user;
+-------------+----------------------+
| User        | max_user_connections |
+-------------+----------------------+
| mariadb.sys |                    0 |
| root        |                    0 |
| mysql       |                    0 |
+-------------+----------------------+
3 rows in set (0.004 sec)
```

*GRANT USAGE ON *.* TO 'root'@'localhost'  WITH MAX_USER_CONNECTIONS 5;*
```mysql
Query OK, 0 rows affected (0.001 sec)
```

*SELECT user, max_user_connections FROM mysql.user;*
```mysql
+-------------+----------------------+
| User        | max_user_connections |
+-------------+----------------------+
| mariadb.sys |                    0 |
| root        |                    5 |
| mysql       |                    0 |
+-------------+----------------------+
3 rows in set (0.002 sec)
```

- Check and remediate `v-253677 STIG`
    
    - What is the problem?
		MariaDB must by default shut down upon audit failure, to include the unavailability of space for more audit log records; or must be configurable to shut down upon audit failure.
    - What is the fix?
		Modify DBMS, OS, or third-party logging application settings to alert appropriate personnel when a specific percentage of log storage capacity is reached.
    - What type of control is being implemented?
    - Is it set properly on your system?

- Check and remediate `v-253678 STIG`
    
    - What is the problem?
	    MariaDB must be configurable to overwrite audit log records, oldest first (First-In-First-Out - FIFO), in the event of unavailability of space for more audit log records.
    - What is the fix?
		Establish a process with accompanying tools for monitoring available disk space and ensuring that sufficient disk space is maintained to continue generating audit logs, overwriting the oldest existing records if necessary.
    - What type of control is being implemented?
    - Is it set properly on your system?

- Check and remediate `v-253734 STIG`
    
    - What is the problem?
	    MariaDB must disable network functions, ports, protocols, and services deemed by the organization to be nonsecure, in accord with the Ports, Protocols, and Services Management (PPSM) guidance.
    - What is the fix?
	    To verify that mariadb system denies specific network functions, locate cnf file and specifically bind ip address to deny (or port):
```bash
        $ ls -la /etc | grep my.cnf
		-rw-r--r--.   1 root root      301 Aug 25 12:45 my.cnf
	      bind-address = 127.0.0.1 #just an example
```
		To specifically change default port (3306) is something different:  port = 1234

```bash
		bind = 10.10.10.10      #as an example 
```

		After making changes to the .cnf file, stop and restart the database service.
    - What type of control is being implemented?
    - Is it set properly on your system?

