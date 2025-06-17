```bash
dpkg -l | grep -i rsyslog
ii  rsyslog                                 8.2312.0-3ubuntu9                        amd64        reliable system and kernel logging daemon
```
```bash
ssh node01 'dpkg -l | grep -i rsyslog'
ii  rsyslog                          8.2312.0-3ubuntu9                       amd64        reliable system and kernel logging daemon
```
```bash
systemctl status rsyslog --no-pager
● rsyslog.service - System Logging Service
     Loaded: loaded (/usr/lib/systemd/system/rsyslog.service; enabled; preset: enabled)
     Active: active (running) since Mon 2025-06-16 19:45:54 UTC; 35min ago
TriggeredBy: ● syslog.socket
       Docs: man:rsyslogd(8)
             man:rsyslog.conf(5)
             https://www.rsyslog.com/doc/
   Main PID: 743 (rsyslogd)
      Tasks: 4 (limit: 2614)
     Memory: 2.5M (peak: 5.0M)
        CPU: 283ms
     CGroup: /system.slice/rsyslog.service
             └─743 /usr/sbin/rsyslogd -n -iNONE

Jun 16 19:45:52 controlplane systemd[1]: Starting rsyslog.service - System Logging Service...
Jun 16 19:45:54 controlplane systemd[1]: Started rsyslog.service - System Logging Service.
Jun 16 19:45:54 controlplane rsyslogd[743]: imuxsock: Acquired UNIX socket '/run/systemd/journal/syslog' (fd 3) from systemd.  [v8.2312.0]
Jun 16 19:45:54 controlplane rsyslogd[743]: rsyslogd's groupid changed to 102
Jun 16 19:45:54 controlplane rsyslogd[743]: rsyslogd's userid changed to 102
Jun 16 19:45:54 controlplane rsyslogd[743]: [origin software="rsyslogd" swVersion="8.2312.0" x-pid="743" x-info="https://www.rsyslog.com"] start
controlplane:~$ ssh node01 'systemctl status rsyslog'
● rsyslog.service - System Logging Service
     Loaded: loaded (/usr/lib/systemd/system/rsyslog.service; enabled; preset: enabled)
     Active: active (running) since Mon 2025-06-16 19:45:53 UTC; 35min ago
TriggeredBy: ● syslog.socket
       Docs: man:rsyslogd(8)
             man:rsyslog.conf(5)
             https://www.rsyslog.com/doc/
    Process: 597 ExecStartPre=/usr/lib/rsyslog/reload-apparmor-profile (code=exited, status=0/SUCCESS)
   Main PID: 688 (rsyslogd)
      Tasks: 4 (limit: 2320)
     Memory: 3.3M (peak: 5.0M)
        CPU: 200ms
     CGroup: /system.slice/rsyslog.service
             └─688 /usr/sbin/rsyslogd -n -iNONE

Jun 16 19:45:51 node01 systemd[1]: Starting rsyslog.service - System Logging Service...
Jun 16 19:45:53 node01 systemd[1]: Started rsyslog.service - System Logging Service.
Jun 16 19:45:53 node01 rsyslogd[688]: imuxsock: Acquired UNIX socket '/run/systemd/journal/syslog' (fd 3) from systemd.  [v8.2312.0]
Jun 16 19:45:53 node01 rsyslogd[688]: rsyslogd's groupid changed to 102
Jun 16 19:45:53 node01 rsyslogd[688]: rsyslogd's userid changed to 102
Jun 16 19:45:53 node01 rsyslogd[688]: [origin software="rsyslogd" swVersion="8.2312.0" x-pid="688" x-info="https://www.rsyslog.com"] start
```
```bash
ss -ntulp | grep 514
udp   UNCONN 0      0                                0.0.0.0:514        0.0.0.0:*    users:(("rsyslogd",pid=21419,fd=5))       
udp   UNCONN 0      0                                   [::]:514           [::]:*    users:(("rsyslogd",pid=21419,fd=6))
```


- Why do we split out the logs in this lab? Why don't we just aggregated them to one place?
	    Easier/faster to find information in separate file than in one place
    - What do we split them out by? Hostname
    - How does that template configuration work? 
	    - Define the configuration & use the configuration in a rule
- Are we securing this communication in any way, or do we still need to configure that?
	- No,  the communication is not encrypted between the machines so it needs to be setup
	

```bash
ss -ntulp | grep grafana
tcp   LISTEN 0      4096                                   *:3000             *:*    users:(("grafana",pid=20594,fd=11))                    
controlplane:~$ ss -ntulp | grep 3000
tcp   LISTEN 0      4096                                   *:3000             *:*    users:(("grafana",pid=20594,fd=11))
```
```bash
ss -ntulp | grep 3100
tcp   LISTEN 0      4096                                   *:3100             *:*    users:(("loki-linux-amd6",pid=29592,fd=8))
```
```bash
systemctl status loki.service --no-pager
● loki.service - Loki Startup
     Loaded: loaded (/etc/systemd/system/loki.service; enabled; preset: enabled)
     Active: active (running) since Mon 2025-06-16 21:35:47 UTC; 6s ago
   Main PID: 29592 (loki-linux-amd6)
      Tasks: 7 (limit: 2614)
     Memory: 20.7M (peak: 20.9M)
        CPU: 136ms
     CGroup: /system.slice/loki.service
             └─29592 /opt/loki/loki-linux-amd64 -config.file=/opt/loki/loki-local-config.yaml

Jun 16 21:35:52 controlplane loki-linux-amd64[29592]: level=info ts=2025-06-16T21:35:52.850171168Z caller=compactor.go:474 msg="this instance has been chosen to run the comp…ng compactor"
Jun 16 21:35:52 controlplane loki-linux-amd64[29592]: level=info ts=2025-06-16T21:35:52.850264743Z caller=compactor.go:503 msg="waiting 10m0s for ring to stay stable and pre…ng compactor"
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646511663Z caller=mock.go:186 msg="Get - deadline exceeded" key=collectors/scheduler
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646563659Z caller=mock.go:150 msg=Get key=collectors/scheduler wait_index=5
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646578147Z caller=mock.go:186 msg="Get - deadline exceeded" key=collectors/compactor
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.64658833Z caller=mock.go:150 msg=Get key=collectors/compactor wait_index=8
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646596112Z caller=mock.go:186 msg="Get - deadline exceeded" key=collectors/distributor
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646605672Z caller=mock.go:150 msg=Get key=collectors/distributor wait_index=4
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646621187Z caller=mock.go:186 msg="Get - deadline exceeded" key=collectors/ring
Jun 16 21:35:53 controlplane loki-linux-amd64[29592]: level=debug ts=2025-06-16T21:35:53.646631499Z caller=mock.go:150 msg=Get key=collectors/ring wait_index=7
Hint: Some lines were ellipsized, use -l to show in full.
```
```bash
systemctl status promtail.service --no-pager
ps -ef | grep [p]romtail
root       33149       1  1 21:42 ?        00:00:00 /opt/promtail/promtail-linux-amd64 -config.file=/opt/promtail/promtail-local-config.yaml

systemctl status promtail.service --no-pager
● promtail.service - Promtail Service Startup
     Loaded: loaded (/etc/systemd/system/promtail.service; enabled; preset: enabled)
     Active: active (running) since Mon 2025-06-16 21:42:35 UTC; 3s ago
   Main PID: 33149 (promtail-linux-)
      Tasks: 8 (limit: 2614)
     Memory: 14.8M (peak: 15.1M)
        CPU: 70ms
     CGroup: /system.slice/promtail.service
             └─33149 /opt/promtail/promtail-linux-amd64 -config.file=/opt/promtail/promtail-local-config.yaml

Jun 16 21:42:35 controlplane systemd[1]: Started promtail.service - Promtail Service Startup.
Jun 16 21:42:35 controlplane promtail-linux-amd64[33149]: level=info ts=2025-06-16T21:42:35.560141679Z caller=promtail.go:123 msg="Reloading configuration file" md5sum=83f74…be7f5eff283fd
Jun 16 21:42:35 controlplane promtail-linux-amd64[33149]: level=info ts=2025-06-16T21:42:35.562222774Z caller=server.go:323 http=[::]:9080 grpc=[::]:40277 msg="server listen…on addresses"
Jun 16 21:42:35 controlplane promtail-linux-amd64[33149]: level=info ts=2025-06-16T21:42:35.562391113Z caller=main.go:171 msg="Starting Promtail" version="(version=HEAD-e0af…n=e0af1cc8a)"
Jun 16 21:42:35 controlplane promtail-linux-amd64[33149]: level=warn ts=2025-06-16T21:42:35.583832346Z caller=promtail.go:220 msg="enable watchConfig"
Hint: Some lines were ellipsized, use -l to show in full.
controlplane:/opt/promtail$ ps -ef | grep [p]romtail
root       33149       1  1 21:42 ?        00:00:00 /opt/promtail/promtail-linux-amd64 -config.file=/opt/promtail/promtail-local-config.yaml
```

![[Pasted image 20250616175552.png]]

![[Pasted image 20250616181643.png]]

```bash
curl -G -s "http://localhost:3100/loki/api/v1/query_range" \
--data-urlencode 'query=sum(rate({job="lab_logging"}[10m])) by (level)' \
--data-urlencode 'step=300' | jq
{
  "status": "success",
  "data": {
    "resultType": "matrix",
    "result": [
      {
        "metric": {},
        "values": [
          [
            1750111500,
            "0.006666666666666667"
          ],
          [
            1750111800,
            "0.006666666666666667"
          ],
          [
            1750112100,
            "0.0016666666666666668"
          ],
          [
            1750112400,
            "0.005"
          ]
        ]
      }
    ],
    "stats": {
      "summary": {
        "bytesProcessedPerSecond": 49133,
        "linesProcessedPerSecond": 693,
        "totalBytesProcessed": 496,
        "totalLinesProcessed": 7,
        "execTime": 0.010095027,
        "queueTime": 0.000105999,
        "subqueries": 0,
        "totalEntriesReturned": 1,
        "splits": 3,
        "shards": 3,
        "totalPostFilterLines": 7,
        "totalStructuredMetadataBytesProcessed": 0
      },
      "querier": {
        "store": {
          "totalChunksRef": 0,
          "totalChunksDownloaded": 0,
          "chunksDownloadTime": 0,
          "chunk": {
            "headChunkBytes": 0,
            "headChunkLines": 0,
            "decompressedBytes": 0,
            "decompressedLines": 0,
            "compressedBytes": 0,
            "totalDuplicates": 0,
            "postFilterLines": 0,
            "headChunkStructuredMetadataBytes": 0,
            "decompressedStructuredMetadataBytes": 0
          },
          "chunkRefsFetchTime": 0
        }
      },
      "ingester": {
        "totalReached": 3,
        "totalChunksMatched": 1,
        "totalBatches": 4,
        "totalLinesSent": 7,
        "store": {
          "totalChunksRef": 0,
          "totalChunksDownloaded": 0,
          "chunksDownloadTime": 0,
          "chunk": {
            "headChunkBytes": 496,
            "headChunkLines": 7,
            "decompressedBytes": 0,
            "decompressedLines": 0,
            "compressedBytes": 0,
            "totalDuplicates": 0,
            "postFilterLines": 7,
            "headChunkStructuredMetadataBytes": 0,
            "decompressedStructuredMetadataBytes": 0
          },
          "chunkRefsFetchTime": 1104439
        }
      },
      "cache": {
        "chunk": {
          "entriesFound": 0,
          "entriesRequested": 0,
          "entriesStored": 0,
          "bytesReceived": 0,
          "bytesSent": 0,
          "requests": 0,
          "downloadTime": 0
        },
        "index": {
          "entriesFound": 0,
          "entriesRequested": 0,
          "entriesStored": 0,
          "bytesReceived": 0,
          "bytesSent": 0,
          "requests": 0,
          "downloadTime": 0
        },
        "result": {
          "entriesFound": 0,
          "entriesRequested": 0,
          "entriesStored": 0,
          "bytesReceived": 0,
          "bytesSent": 0,
          "requests": 0,
          "downloadTime": 0
        },
        "statsResult": {
          "entriesFound": 0,
          "entriesRequested": 0,
          "entriesStored": 0,
          "bytesReceived": 0,
          "bytesSent": 0,
          "requests": 0,
          "downloadTime": 0
        }
      }
    }
  }
}
```

```bash
kubectl get all -n kafka
NAME                             READY   STATUS    RESTARTS   AGE
pod/zookeeper-6868cb9466-m24m6   1/1     Running   0          23s

NAME                        TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
service/zookeeper-service   NodePort   10.99.245.191   <none>        2181:30900/TCP   24s

NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/zookeeper   1/1     1            1           24s

NAME                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/zookeeper-6868cb9466   1         1         1       23s
```
```bash
kubectl describe -n kafka svc zookeeper-service
Name:                     zookeeper-service
Namespace:                kafka
Labels:                   app=zookeeper-service
Annotations:              <none>
Selector:                 app=zookeeper
Type:                     NodePort
IP Family Policy:         SingleStack
IP Families:              IPv4
IP:                       10.99.245.191
IPs:                      10.99.245.191
Port:                     zookeeper-port  2181/TCP
TargetPort:               2181/TCP
NodePort:                 zookeeper-port  30900/TCP
Endpoints:                192.168.1.4:2181
Session Affinity:         None
External Traffic Policy:  Cluster
Internal Traffic Policy:  Cluster
Events:                   <none>
```
```bash
kubectl get pods -o wide -n kafka
NAME                            READY   STATUS    RESTARTS   AGE     IP            NODE     NOMINATED NODE   READINESS GATES
kafka-broker-77fdd88cf9-lfzt8   1/1     Running   0          4m20s   192.168.1.5   node01   <none>           <none>
zookeeper-6868cb9466-m24m6      1/1     Running   0          5m30s   192.168.1.4   node01   <none>           <none>
```
```bash
echo "This is my message at $(date)" | kcat -P -b node01:31000 -t System_Logs
Handling connection for 9092
```
```bash
timeout 3 kcat -C -b node01:31000 -t System_Logs
Handling connection for 9092
This is my message at Tue Jun 17 01:38:32 UTC 2025
This is my message at Tue Jun 17 01:38:33 UTC 2025
% Reached end of topic System_Logs [0] at offset 2
```
![[Pasted image 20250616214312.png]]

Can you find any configurations or blogs that describe why you might want to use this architecture or how it has been used in the industry?
	https://www.groundcover.com/blog/kafka-logging
	https://docs.confluent.io/platform/current/kafka/post-deployment.html
	https://www.redpanda.com/guides/kafka-performance-kafka-monitoring
	https://coralogix.com/blog/how-to-maximize-logging-performance-with-kafka/