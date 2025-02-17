
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | Trend Micro Deep Security produce logs describing authentication events |
| `File monitoring` | Trend Micro Deep Security monitor changes made on the host and on the appplications |
| `Network intrusion detection system` | Trend Micro Deep Security monitor the network traffic to prevent intrusions |
| `Network protocol analysis` | Trend Micro Deep Security monitor the network traffic and maintains event logs for audit |
| `Web proxy` | Trend Micro Deep Security monitor HTTP traffic to block malicious payloads and communication with C&C. |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `authentication`, `intrusion_detection` |
| Type | `start` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "AgentAntiMalware.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|<Agent version>|4000000|Eicar_test_file|6|cn1=1 cn1Label=Host ID dvchost=hostname cn2=205 cn2Label=Quarantine File Size cs6=ContainerImageName | ContainerName | ContainerID cs6Label=Container filePath=C:\\Users\\trend\\Desktop\\eicar.exe act=Delete result=Delete msg=Realtime TrendMicroDsMalwareTarget=N/A TrendMicroDsMalwareTargetType=N/A TrendMicroDsFileMD5=44D88612FEA8A8F36DE82E1278ABB02F TrendMicroDsFileSHA1=3395856CE81F2B7382DEE72602F798B642F14140 TrendMicroDsFileSHA256=275A021BBFB6489E54D471899F7DB9D1663FC695EC2FE2A2C4538AABF651FD0F TrendMicroDsDetectionConfidence=95 TrendMicroDsRelevantDetectionNames=Ransom_CERBER.BZC;Ransom_CERBER.C;Ransom_CRYPNISCA.SM",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 6,
            "action": "Delete",
            "reason": "Realtime"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "<Agent version>"
        },
        "rule": {
            "id": "4000000"
        },
        "trendmicro": {
            "TrendMicroDsRelevantDetectionNames": [
                "Ransom_CERBER.BZC",
                "Ransom_CERBER.C",
                "Ransom_CRYPNISCA.SM"
            ],
            "TrendMicroDsDetectionConfidence": "95",
            "TrendMicroDsMalwareTargetType": "N/A",
            "TrendMicroDsMalwareTarget": "N/A",
            "ResourceType": "Other"
        },
        "container": {
            "name": "ContainerImageName | ContainerName | ContainerID"
        },
        "host": {
            "id": "1",
            "name": "hostname"
        },
        "file": {
            "hash": {
                "sha256": "275A021BBFB6489E54D471899F7DB9D1663FC695EC2FE2A2C4538AABF651FD0F",
                "sha1": "3395856CE81F2B7382DEE72602F798B642F14140",
                "md5": "44D88612FEA8A8F36DE82E1278ABB02F"
            },
            "size": 205,
            "path": "C:\\Users\\trend\\Desktop\\eicar.exe"
        },
        "cef": {
            "Name": "Eicar_test_file"
        },
        "related": {
            "hash": [
                "275A021BBFB6489E54D471899F7DB9D1663FC695EC2FE2A2C4538AABF651FD0F",
                "3395856CE81F2B7382DEE72602F798B642F14140",
                "44D88612FEA8A8F36DE82E1278ABB02F"
            ]
        }
    }
    	
	```


=== "ApacheDOS.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|20.0.677|1011466|Apache HTTP Server 'mod_sed' Denial Of Service Vulnerability (CVE-2022-30522)|6|cn1=318 cn1Label=Host ID dvchost=foo.bar.fr TrendMicroDsTenant=Primary TrendMicroDsTenantId=0 dmac=22:22:22:22:22:22 smac=11:11:11:11:11:11 TrendMicroDsFrameType=IP src=2.2.2.2 dst=1.1.1.1 in=0 cs3=DF 0 cs3Label=Fragmentation Bits proto=TCP spt=58407 dpt=443 cs2=ACK cs2Label=TCP Flags cnt=2 act=IDS:Reset cn3=0 cn3Label=DPI Packet Position cs5=0 cs5Label=DPI Stream Position  cs1=\"CVE-2022-30522\" cs1Label=DPI Note cs6=0 cs6Label=DPI Flags\n\n",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 6,
            "action": "IDS:Reset",
            "reason": "Apache HTTP Server 'mod_sed' Denial Of Service Vulnerability (CVE-2022-30522)"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "20.0.677"
        },
        "rule": {
            "id": "1011466"
        },
        "source": {
            "ip": "2.2.2.2",
            "mac": "11:11:11:11:11:11",
            "port": 58407,
            "address": "2.2.2.2"
        },
        "destination": {
            "port": 443,
            "ip": "1.1.1.1",
            "mac": "22:22:22:22:22:22",
            "address": "1.1.1.1"
        },
        "host": {
            "network": {
                "ingress": {
                    "bytes": 0
                }
            },
            "id": "318",
            "name": "foo.bar.fr"
        },
        "trendmicro": {
            "TrendMicroDsFrameType": "IP",
            "TrendMicroDsTenantId": "0",
            "TrendMicroDsTenant": "Primary",
            "FragmentationBits": "DF 0",
            "TCPFlags": [
                "ACK"
            ],
            "ResourceType": "Other"
        },
        "cef": {
            "Name": "Apache HTTP Server 'mod_sed' Denial Of Service Vulnerability (CVE-2022-30522)"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "ApplicationControl.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|10.2.229|6001200|AppControl detectOnly|6|cn1=202 cn1Label=Host ID dvc=192.168.33.128 TrendMicroDsTenant=Primary TrendMicroDsTenantId=0 fileHash=80D4AC182F97D2AB48EE4310AC51DA5974167C596D133D64A83107B9069745E0 suser=root suid=0 act=detectOnly filePath=/home/user1/Desktop/Directory1//heartbeatSync.sh fsize=20 aggregationType=0 repeatCount=1 cs1=notWhitelisted cs1Label=actionReason cs2=0CC9713BA896193A527213D9C94892D41797EB7C cs2Label=sha1 cs3=7EA8EF10BEB2E9876D4D7F7E5A46CF8D cs3Label=md5",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 6,
            "action": "detectOnly",
            "reason": "notWhitelisted"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "10.2.229"
        },
        "rule": {
            "id": "6001200"
        },
        "file": {
            "size": 20,
            "hash": {
                "sha1": "0CC9713BA896193A527213D9C94892D41797EB7C",
                "md5": "7EA8EF10BEB2E9876D4D7F7E5A46CF8D"
            },
            "path": "/home/user1/Desktop/Directory1//heartbeatSync.sh"
        },
        "source": {
            "user": {
                "name": "root"
            }
        },
        "host": {
            "ip": [
                "192.168.33.128"
            ],
            "id": "202"
        },
        "trendmicro": {
            "TrendMicroDsTenantId": "0",
            "TrendMicroDsTenant": "Primary",
            "ResourceType": "Other"
        },
        "cef": {
            "Name": "AppControl detectOnly"
        },
        "related": {
            "hash": [
                "0CC9713BA896193A527213D9C94892D41797EB7C",
                "7EA8EF10BEB2E9876D4D7F7E5A46CF8D"
            ],
            "ip": [
                "192.168.33.128"
            ],
            "user": [
                "root"
            ]
        }
    }
    	
	```


=== "DeviceControl.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|50.0.1063|7000000|Device Control DeviceControl|6|cn1=1 cn1Label=Host ID dvchost=test-hostname TrendMicroDsTenant=tenantName TrendMicroDsTenantId=1 device=deviceName processName=processName1 fileName=/tmp/some_path2 vendor=vendorName serial=aaaa-bbbb-cccc model=modelName computerName=computerName domainName=computerDomain deviceType=0 permission=0",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 6,
            "reason": "Device Control DeviceControl"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "50.0.1063"
        },
        "rule": {
            "id": "7000000"
        },
        "trendmicro": {
            "TrendMicroDsTenantId": "1",
            "TrendMicroDsTenant": "tenantName",
            "ResourceType": "Other"
        },
        "host": {
            "id": "1",
            "name": "test-hostname"
        },
        "cef": {
            "Name": "Device Control DeviceControl"
        }
    }
    	
	```


=== "FirewallEventLog.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|<Agent version>|20|Log for TCP Port 80|0|cn1=1 cn1Label=Host ID dvc=hostname act=Log dmac=00:50:56:F5:7F:47 smac=00:0C:29:EB:35:DE TrendMicroDsFrameType=IP src=192.168.126.150 dst=72.14.204.147 out=1019 cs3=DF MF cs3Label=Fragmentation Bits proto=TCP spt=49617 dpt=80 cs2=0x00 ACK PSH cs2Label=TCP Flags cnt=1 TrendMicroDsPacketData=AFB...",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "action": "Log",
            "reason": "Log for TCP Port 80"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "<Agent version>"
        },
        "rule": {
            "id": "20",
            "name": "Log-only Firewall rule"
        },
        "source": {
            "ip": "192.168.126.150",
            "mac": "00:0C:29:EB:35:DE",
            "port": 49617,
            "address": "192.168.126.150"
        },
        "destination": {
            "port": 80,
            "ip": "72.14.204.147",
            "mac": "00:50:56:F5:7F:47",
            "address": "72.14.204.147"
        },
        "host": {
            "ip": [
                "hostname"
            ],
            "network": {
                "egress": {
                    "bytes": 1019
                }
            },
            "id": "1"
        },
        "trendmicro": {
            "TrendMicroDsFrameType": "IP",
            "FragmentationBits": "DF MF",
            "TCPFlags": [
                "0x00",
                "ACK",
                "PSH"
            ],
            "ResourceType": "Other"
        },
        "cef": {
            "Name": "Log for TCP Port 80"
        },
        "related": {
            "ip": [
                "192.168.126.150",
                "72.14.204.147",
                "hostname"
            ]
        }
    }
    	
	```


=== "IntegrityMonitoring.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|<Agent version>|30|New Integrity Monitoring Rule|6|cn1=1 cn1Label=Host ID dvchost=hostname act=updated filePath=c:\\windows\\message.dll suser=admin sproc=C:\\Windows\\System32\\notepad.exe msg=lastModified,sha1,size",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 6,
            "action": "updated",
            "reason": "lastModified,sha1,size"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "<Agent version>"
        },
        "rule": {
            "id": "30",
            "name": "Custom Integrity Monitoring rule"
        },
        "source": {
            "user": {
                "name": "admin"
            }
        },
        "trendmicro": {
            "ResourceType": "Other"
        },
        "host": {
            "id": "1",
            "name": "hostname"
        },
        "file": {
            "path": "c:\\windows\\message.dll"
        },
        "cef": {
            "Name": "New Integrity Monitoring Rule"
        },
        "related": {
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "IntrusionPrevention.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|<Agent version>|1001111|Test Intrusion Prevention Rule|3|cn1=1 cn1Label=Host ID dvchost=hostname dmac=00:50:56:F5:7F:47 smac=00:0C:29:EB:35:DE TrendMicroDsFrameType=IP src=192.168.126.150 dst=72.14.204.105 out=1093 cs3=DF MF cs3Label=Fragmentation Bits proto=TCP spt=49786 dpt=80 cs2=0x00 ACK PSH cs2Label=TCP Flags cnt=1 act=IDS:Reset cn3=10 cn3Label=Intrusion Prevention Packet Position cs5=10 cs5Label=Intrusion Prevention Stream Position cs6=8 cs6Label=Intrusion Prevention Flags TrendMicroDsPacketData=R0VUIC9zP3...",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 3,
            "action": "IDS:Reset",
            "reason": "Test Intrusion Prevention Rule"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "<Agent version>"
        },
        "rule": {
            "id": "1001111"
        },
        "source": {
            "ip": "192.168.126.150",
            "mac": "00:0C:29:EB:35:DE",
            "port": 49786,
            "address": "192.168.126.150"
        },
        "destination": {
            "port": 80,
            "ip": "72.14.204.105",
            "mac": "00:50:56:F5:7F:47",
            "address": "72.14.204.105"
        },
        "host": {
            "network": {
                "egress": {
                    "bytes": 1093
                }
            },
            "id": "1",
            "name": "hostname"
        },
        "trendmicro": {
            "TrendMicroDsFrameType": "IP",
            "IntrusionPreventionStreamPosition": "10",
            "IntrusionPreventionFlags": "8",
            "FragmentationBits": "DF MF",
            "TCPFlags": [
                "0x00",
                "ACK",
                "PSH"
            ],
            "ResourceType": "Other"
        },
        "cef": {
            "Name": "Test Intrusion Prevention Rule"
        },
        "related": {
            "ip": [
                "192.168.126.150",
                "72.14.204.105"
            ]
        }
    }
    	
	```


=== "LogInspection.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|<Agent version>|3002795|Microsoft Windows Events|8|cn1=1 cn1Label=Host ID dvchost=hostname cs1Label=LI Description cs1=Multiple Windows Logon Failures fname=Security src=127.0.0.1 duser=(no user) shost=WIN-RM6HM42G65V msg=WinEvtLog Security: AUDIT_FAILURE(4625): Microsoft-Windows-Security-Auditing: (no user): no domain: WIN-RM6HM42G65V: An account failed to log on. Subject: ..",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 8,
            "reason": "WinEvtLog Security: AUDIT_FAILURE(4625): Microsoft-Windows-Security-Auditing: (no user): no domain: WIN-RM6HM42G65V: An account failed to log on. Subject: .."
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "<Agent version>"
        },
        "rule": {
            "id": "3002795"
        },
        "file": {
            "name": "Security"
        },
        "source": {
            "ip": "127.0.0.1",
            "address": "127.0.0.1"
        },
        "destination": {
            "user": {
                "name": "(no user)"
            }
        },
        "host": {
            "hostname": "WIN-RM6HM42G65V",
            "id": "1",
            "name": "hostname"
        },
        "trendmicro": {
            "LogInspectionDescription": "Multiple Windows Logon Failures",
            "ResourceType": "Other"
        },
        "cef": {
            "Name": "Microsoft Windows Events"
        },
        "related": {
            "hosts": [
                "WIN-RM6HM42G65V"
            ],
            "user": [
                "(no user)"
            ],
            "ip": [
                "127.0.0.1"
            ]
        }
    }
    	
	```


=== "SystemEventLog.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Workload Security Manager|<Workload Security version>|600|User Signed In|3|src=10.52.116.160 suser=admin target=admin msg=User signed in from 2001:db8::5",
        "event": {
            "kind": "event",
            "category": [
                "authentication"
            ],
            "type": [
                "info"
            ],
            "severity": 3,
            "reason": "User signed in from 2001:db8::5"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Workload Security Manager",
            "version": "<Workload Security version>"
        },
        "rule": {
            "id": "600"
        },
        "source": {
            "ip": "10.52.116.160",
            "user": {
                "name": "admin"
            },
            "address": "10.52.116.160"
        },
        "trendmicro": {
            "ResourceType": "Other"
        },
        "cef": {
            "Name": "User Signed In"
        },
        "related": {
            "user": [
                "admin"
            ],
            "ip": [
                "10.52.116.160"
            ]
        }
    }
    	
	```


=== "WebReputation.json"

    ```json
	
    {
        "message": "CEF:0|Trend Micro|Deep Security Agent|<Agent version>|5000000|WebReputation|5|cn1=1 cn1Label=Host ID dvchost=hostname request=example.com msg=Blocked By Admin",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "severity": 5,
            "reason": "Blocked By Admin"
        },
        "observer": {
            "vendor": "Trend Micro",
            "type": "Deep Security Agent",
            "version": "<Agent version>"
        },
        "rule": {
            "id": "5000000"
        },
        "url": {
            "original": "example.com",
            "path": "example.com"
        },
        "trendmicro": {
            "ResourceType": "Other"
        },
        "host": {
            "id": "1",
            "name": "hostname"
        },
        "cef": {
            "Name": "WebReputation"
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`container.name` | `keyword` | Container name. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.mac` | `keyword` | MAC address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`destination.user.name` | `keyword` | Short name or login of the user. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.risk_score_norm` | `float` | Normalized risk score or priority of the event (0-100). |
|`event.severity` | `long` | Numeric severity of the event. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.hash.md5` | `keyword` | MD5 hash. |
|`file.hash.sha1` | `keyword` | SHA1 hash. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`file.size` | `long` | File size in bytes. |
|`host.hostname` | `keyword` | Hostname of the host. |
|`host.id` | `keyword` | Unique host id. |
|`host.ip` | `ip` | Host ip addresses. |
|`host.name` | `keyword` | Name of the host. |
|`host.network.egress.bytes` | `long` | The number of bytes sent on all network interfaces. |
|`host.network.ingress.bytes` | `long` | The number of bytes received on all network interfaces. |
|`network.protocol` | `keyword` | Application protocol name. |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`observer.version` | `keyword` | Observer version. |
|`process.command_line` | `wildcard` | Full command line that started the process. |
|`process.name` | `keyword` | Process name. |
|`rule.id` | `keyword` | Rule ID |
|`source.ip` | `ip` | IP address of the source. |
|`source.mac` | `keyword` | MAC address of the source. |
|`source.port` | `long` | Port of the source. |
|`source.user.name` | `keyword` | Short name or login of the user. |
|`trendmicro.FragmentationBits` | `keyword` | Fragmentation Bits |
|`trendmicro.IntrusionPreventionFlags` | `keyword` | Intrusion Prevention Flags |
|`trendmicro.IntrusionPreventionStreamPosition` | `keyword` | Intrusion Prevention Stream Position |
|`trendmicro.LogInspectionDescription` | `keyword` |  |
|`trendmicro.ResourceTypeId` | `keyword` | Resource Type identifier |
|`trendmicro.TCPFlags` | `keyword` | TCP Flags |
|`trendmicro.TrendMicroDsRelevantDetectionNames` | `keyword` |  |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |

