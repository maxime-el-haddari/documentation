
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Host network interface` | every packets are logged and information on the outcome, the source/destination are extracted |
| `Network device logs` | ACL logs are examined in detail |
| `Network protocol analysis` | ICMP, TCP and UDP packets are fully analyzed |
| `Web proxy` | Cisco Web Security Appliance logs provide information about the connected client and the requested resource |
| `Web logs` | Cisco Web Security Appliance logs provide information about the connected client and the requested resource |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `alert`, `event` |
| Category | `file`, `intrusion_detection`, `malware`, `network` |
| Type | `change`, `connection`, `end`, `info`, `start` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_106001.json"

    ```json
	
    {
        "message": "%FTD-2-106001: Inbound TCP connection denied from 172.16.10.234/901 to 192.168.122.55/111 flags SYN  on interface LAN",
        "event": {
            "category": [
                "network"
            ],
            "code": "106001",
            "kind": "event"
        },
        "action": {
            "name": "denied",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "192.168.122.55",
            "port": 111,
            "address": "192.168.122.55"
        },
        "network": {
            "direction": "Inbound",
            "transport": "tcp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Firepower Threat Defense"
        },
        "source": {
            "ip": "172.16.10.234",
            "port": 901,
            "address": "172.16.10.234"
        },
        "related": {
            "ip": [
                "172.16.10.234",
                "192.168.122.55"
            ]
        }
    }
    	
	```


=== "test_106006.json"

    ```json
	
    {
        "message": "%FTD-2-106006: Deny inbound UDP from 172.16.10.234/901 to 192.168.122.55/111 on interface LAN",
        "event": {
            "category": [
                "network"
            ],
            "code": "106006",
            "kind": "event"
        },
        "action": {
            "name": "deny",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "192.168.122.55",
            "port": 111,
            "address": "192.168.122.55"
        },
        "network": {
            "direction": "inbound",
            "transport": "udp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Firepower Threat Defense"
        },
        "source": {
            "ip": "172.16.10.234",
            "port": 901,
            "address": "172.16.10.234"
        },
        "related": {
            "ip": [
                "172.16.10.234",
                "192.168.122.55"
            ]
        }
    }
    	
	```


=== "test_430002.json"

    ```json
	
    {
        "message": "%NGIPS-1-430002: EventPriority: Low, DeviceUUID: b2433c5c-a6a1-11eb-a6e7-be0b9833091f, InstanceID: 2, FirstPacketSecond: 2021-04-30T11:31:19Z, ConnectionID: 4, AccessControlRuleAction: Allow, SrcIP: 172.16.10.10, DstIP: 172.16.20.10, ICMPType: Echo Request, ICMPCode: No Code, Protocol: icmp, IngressInterface: inside, EgressInterface: outside, ACPolicy: Default Allow All Traffic, AccessControlRuleName: test, Client: ICMP client, ApplicationProtocol: ICMP, InitiatorPackets: 1, ResponderPackets: 0, InitiatorBytes: 74, ResponderBytes: 0, NAPPolicy: Balanced Security and Connectivity",
        "event": {
            "code": "430002",
            "kind": "event",
            "category": [
                "network"
            ],
            "action": "connection-started",
            "type": [
                "connection",
                "start"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Secure IPS"
        },
        "action": {
            "target": "network-traffic"
        },
        "destination": {
            "bytes": 0,
            "ip": "172.16.20.10",
            "packets": 0,
            "address": "172.16.20.10"
        },
        "log": {
            "level": "Low"
        },
        "network": {
            "application": "icmp client",
            "protocol": "ICMP",
            "transport": "icmp"
        },
        "rule": {
            "name": "test",
            "ruleset": "Default Allow All Traffic"
        },
        "source": {
            "bytes": 74,
            "ip": "172.16.10.10",
            "packets": 1,
            "address": "172.16.10.10"
        },
        "related": {
            "ip": [
                "172.16.10.10",
                "172.16.20.10"
            ]
        }
    }
    	
	```


=== "test_430003.json"

    ```json
	
    {
        "message": "%NGIPS-1-430003: EventPriority: Low, DeviceUUID: e8566508-eaa9-11e5-860f-de3e305d8269, InstanceID: 3, FirstPacketSecond: 2020-02-04T08:45:34Z, ConnectionID: 34774, AccessControlRuleAction: <br/>Block with reset, SrcIP: 93.157.158.93, DstIP: 10.1.9.9, SrcPort: 13723, DstPort: 80, Protocol: tcp, IngressInterface: outside, EgressInterface: seversDMZ, ACPolicy: Basic IPS/IDS and GeoIP block foreign contries, AccessControlRuleName: GeoBlock other Countries, Prefilter Policy: Unknown, ConnectionDuration: 0, InitiatorPackets: 1, ResponderPackets: 0, InitiatorBytes: 54, ResponderBytes: 0, NAPPolicy: Balanced Security and Connectivity",
        "event": {
            "code": "430003",
            "kind": "event",
            "category": [
                "network"
            ],
            "action": "connection-finished",
            "type": [
                "connection",
                "end"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Secure IPS"
        },
        "action": {
            "target": "network-traffic"
        },
        "destination": {
            "bytes": 0,
            "ip": "10.1.9.9",
            "packets": 0,
            "port": 80,
            "address": "10.1.9.9"
        },
        "log": {
            "level": "Low"
        },
        "network": {
            "transport": "tcp"
        },
        "rule": {
            "name": "GeoBlock other Countries",
            "ruleset": "Basic IPS/IDS and GeoIP block foreign contries"
        },
        "source": {
            "bytes": 54,
            "ip": "93.157.158.93",
            "packets": 1,
            "port": 13723,
            "address": "93.157.158.93"
        },
        "related": {
            "ip": [
                "10.1.9.9",
                "93.157.158.93"
            ]
        }
    }
    	
	```


=== "test_430005.json"

    ```json
	
    {
        "message": "%FTD-1-430005: SrcIP: 10.0.1.20, DstIP: 81.2.69.144, SrcPort: 46004, DstPort: 80, Protocol: tcp, FileDirection: Download, FileAction: Malware Cloud Lookup, FileSHA256: 2546dcffc5ad854d4ddc64fbf056871cd5a00f2471cb7a5bfd4ac23b6e9eedad, SHA_Disposition: Unavailable, SperoDisposition: Spero detection not performed on file, ThreatName: Win.Ransomware.Eicar::95.sbx.tg, FileName: eicar_com.zip, FileType: ZIP, FileSize: 184, ApplicationProtocol: HTTP, Client: cURL, User: No Authentication Required, FirstPacketSecond: 2019-08-16T09:39:02Z, FilePolicy: malware-and-file-policy, FileStorageStatus: Not Stored (Disposition Was Pending), FileSandboxStatus: File Size Is Too Small, URI: http://www.eicar.org/download/eicar_com.zip",
        "event": {
            "code": "430005",
            "kind": "alert",
            "category": [
                "malware"
            ],
            "action": "malware-detected",
            "type": [
                "info"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Firepower Threat Defense"
        },
        "action": {
            "target": "network-traffic"
        },
        "cisco": {
            "ftd": {
                "file_sandbox_status": "File Size Is Too Small",
                "file_storage_status": "Not Stored (Disposition Was Pending)",
                "sha_disposition": "Unavailable",
                "spero_disposition": "Spero detection not performed on file"
            }
        },
        "destination": {
            "ip": "81.2.69.144",
            "port": 80,
            "address": "81.2.69.144"
        },
        "file": {
            "extension": "zip",
            "hash": {
                "sha256": "2546dcffc5ad854d4ddc64fbf056871cd5a00f2471cb7a5bfd4ac23b6e9eedad"
            },
            "name": "eicar_com.zip",
            "size": 184
        },
        "network": {
            "application": "curl",
            "protocol": "HTTP",
            "transport": "tcp"
        },
        "source": {
            "ip": "10.0.1.20",
            "port": 46004,
            "address": "10.0.1.20"
        },
        "threat": {
            "software": {
                "name": "Win.Ransomware.Eicar::95.sbx.tg"
            }
        },
        "url": {
            "original": "http://www.eicar.org/download/eicar_com.zip",
            "domain": "www.eicar.org",
            "top_level_domain": "org",
            "subdomain": "www",
            "registered_domain": "eicar.org",
            "scheme": "http",
            "path": "/download/eicar_com.zip",
            "port": 80
        },
        "user": {
            "name": "No Authentication Required"
        },
        "related": {
            "hash": [
                "2546dcffc5ad854d4ddc64fbf056871cd5a00f2471cb7a5bfd4ac23b6e9eedad"
            ],
            "ip": [
                "10.0.1.20",
                "81.2.69.144"
            ],
            "user": [
                "No Authentication Required"
            ]
        }
    }
    	
	```


=== "test_ASA_106012.json"

    ```json
	
    {
        "message": "%ASA-6-106012: Deny IP from 192.168.122.143 to 224.0.0.22, IP options: \"Router Alert\"",
        "event": {
            "category": [
                "network"
            ],
            "code": "106012",
            "kind": "event"
        },
        "action": {
            "name": "deny",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "224.0.0.22",
            "address": "224.0.0.22"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "192.168.122.143",
            "address": "192.168.122.143"
        },
        "related": {
            "ip": [
                "192.168.122.143",
                "224.0.0.22"
            ]
        }
    }
    	
	```


=== "test_ASA_106015.json"

    ```json
	
    {
        "message": "%ASA-6-106015: Deny TCP (no connection) from 10.9.4.3/52675 to 161.5.222.141/443 flags FIN ACK on interface ACME_interface",
        "event": {
            "code": "106015",
            "kind": "event",
            "category": [
                "network"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "action": {
            "name": "deny",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "161.5.222.141",
            "port": 443,
            "address": "161.5.222.141"
        },
        "network": {
            "transport": "tcp"
        },
        "source": {
            "ip": "10.9.4.3",
            "port": 52675,
            "address": "10.9.4.3"
        },
        "related": {
            "ip": [
                "10.9.4.3",
                "161.5.222.141"
            ]
        }
    }
    	
	```


=== "test_ASA_106023.json"

    ```json
	
    {
        "message": "%ASA-4-106023: Deny udp src ACMEsL:10.0.200.29/320 dst identity:224.0.1.129/320 by access-group \"ACME_group\" [0x0, 0x0]",
        "event": {
            "code": "106023",
            "kind": "event",
            "category": [
                "network"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "action": {
            "name": "deny",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "224.0.1.129",
            "port": 320,
            "address": "224.0.1.129"
        },
        "network": {
            "transport": "udp"
        },
        "source": {
            "ip": "10.0.200.29",
            "port": 320,
            "address": "10.0.200.29"
        },
        "related": {
            "ip": [
                "10.0.200.29",
                "224.0.1.129"
            ]
        }
    }
    	
	```


=== "test_ASA_106100.json"

    ```json
	
    {
        "message": "%ASA-6-106100: access-list ACME_INFRA permitted udp ACME_INFRA/10.1.0.16(42592) -> ACME/10.1.1.76(161) hit-cnt 1 first hit [0x42666c4c, 0x05739900]",
        "event": {
            "code": "106100",
            "kind": "event",
            "category": [
                "network"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "action": {
            "name": "permitted",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "10.1.1.76",
            "port": 161,
            "address": "10.1.1.76"
        },
        "network": {
            "transport": "udp"
        },
        "source": {
            "ip": "10.1.0.16",
            "port": 42592,
            "address": "10.1.0.16"
        },
        "related": {
            "ip": [
                "10.1.0.16",
                "10.1.1.76"
            ]
        }
    }
    	
	```


=== "test_ASA_110003.json"

    ```json
	
    {
        "message": "%ASA-6-110003: Routing failed to locate next hop for icmp from WAN:10.11.0.2/0 to WAN:10.112.115.1/0",
        "event": {
            "category": [
                "network"
            ],
            "code": "110003",
            "kind": "event"
        },
        "action": {
            "name": "routing failed to locate next hop for icmp",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "10.112.115.1",
            "address": "10.112.115.1"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "10.11.0.2",
            "address": "10.11.0.2"
        },
        "related": {
            "ip": [
                "10.11.0.2",
                "10.112.115.1"
            ]
        }
    }
    	
	```


=== "test_ASA_302013.json"

    ```json
	
    {
        "message": "%ASA-6-302013: Built inbound TCP connection 1800234408 for TTA-ACME-VDO_CAM:10.1.7.248/40454 (10.1.7.248/40454) to TTA-ACME-SRV_INFRA:10.1.0.10/53 (10.1.0.10/53)",
        "event": {
            "code": "302013",
            "kind": "event",
            "category": [
                "network"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "action": {
            "name": "built",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "10.1.0.10",
            "port": 53,
            "nat": {
                "ip": "10.1.0.10",
                "port": 53
            },
            "address": "10.1.0.10"
        },
        "network": {
            "direction": "inbound",
            "transport": "tcp"
        },
        "source": {
            "ip": "10.1.7.248",
            "port": 40454,
            "nat": {
                "ip": "10.1.7.248",
                "port": 40454
            },
            "address": "10.1.7.248"
        },
        "related": {
            "ip": [
                "10.1.0.10",
                "10.1.7.248"
            ]
        }
    }
    	
	```


=== "test_ASA_302014.json"

    ```json
	
    {
        "message": "%ASA-6-302014: Teardown TCP connection 3142352458 for Pika:10.79.66.29/47864 to pa_asa:10.79.2.75/80 duration 5:55:15 bytes 0 TCP FINs from Pika",
        "event": {
            "code": "302014",
            "kind": "event",
            "category": [
                "network"
            ]
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "action": {
            "target": "network-traffic",
            "name": "teardown"
        },
        "destination": {
            "ip": "10.79.2.75",
            "port": 80,
            "address": "10.79.2.75"
        },
        "network": {
            "bytes": 0,
            "transport": "tcp"
        },
        "source": {
            "ip": "10.79.66.29",
            "port": 47864,
            "address": "10.79.66.29"
        },
        "related": {
            "ip": [
                "10.79.2.75",
                "10.79.66.29"
            ]
        }
    }
    	
	```


=== "test_ASA_302020.json"

    ```json
	
    {
        "message": "%ASA-6-302020: Built inbound ICMP connection for faddr 47.241.116.84/10800 gaddr 10.11.0.2/0 laddr 10.11.0.2/0",
        "event": {
            "category": [
                "network"
            ],
            "code": "302020",
            "kind": "event"
        },
        "action": {
            "name": "built",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "47.241.116.84",
            "port": 10800,
            "address": "47.241.116.84"
        },
        "network": {
            "direction": "inbound",
            "transport": "icmp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "10.11.0.2",
            "address": "10.11.0.2"
        },
        "related": {
            "ip": [
                "10.11.0.2",
                "47.241.116.84"
            ]
        }
    }
    	
	```


=== "test_ASA_302021.json"

    ```json
	
    {
        "message": "%ASA-6-302021: Teardown ICMP connection for faddr 172.16.10.208/2189 gaddr 172.16.19.90/0 laddr 172.16.19.90/0 (karibou)",
        "event": {
            "category": [
                "network"
            ],
            "code": "302021",
            "kind": "event"
        },
        "action": {
            "name": "teardown",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "172.16.10.208",
            "port": 2189,
            "address": "172.16.10.208"
        },
        "network": {
            "transport": "icmp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "172.16.19.90",
            "address": "172.16.19.90"
        },
        "user": {
            "name": "karibou"
        },
        "related": {
            "ip": [
                "172.16.10.208",
                "172.16.19.90"
            ],
            "user": [
                "karibou"
            ]
        }
    }
    	
	```


=== "test_ASA_305011.json"

    ```json
	
    {
        "message": "%ASA-6-305011: Built dynamic TCP translation from interco_pa_asa:10.79.16.23/35928 to dmz-gce:126.189.129.55/35928",
        "event": {
            "category": [
                "network"
            ],
            "code": "305011",
            "kind": "event"
        },
        "action": {
            "name": "built",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "126.189.129.55",
            "port": 35928,
            "address": "126.189.129.55"
        },
        "network": {
            "transport": "tcp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "10.79.16.23",
            "port": 35928,
            "address": "10.79.16.23"
        },
        "related": {
            "ip": [
                "10.79.16.23",
                "126.189.129.55"
            ]
        }
    }
    	
	```


=== "test_ASA_305012.json"

    ```json
	
    {
        "message": "%ASA-6-305012: Teardown dynamic TCP translation from interco_asa:10.79.16.24/55924 to dmz:12.18.129.56/55924 duration 0:00:15",
        "event": {
            "category": [
                "network"
            ],
            "code": "305012",
            "kind": "event"
        },
        "action": {
            "name": "teardown",
            "target": "network-traffic"
        },
        "destination": {
            "ip": "12.18.129.56",
            "port": 55924,
            "address": "12.18.129.56"
        },
        "network": {
            "transport": "tcp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "10.79.16.24",
            "port": 55924,
            "address": "10.79.16.24"
        },
        "related": {
            "ip": [
                "10.79.16.24",
                "12.18.129.56"
            ]
        }
    }
    	
	```


=== "test_ASA_313008.json"

    ```json
	
    {
        "message": "%ASA-3-313008: Denied IPv6-ICMP type=136, code=0 from fe80::f037:5fbc:b824:230d on interface NEA-FOR-WIFOR",
        "event": {
            "category": [
                "network"
            ],
            "code": "313008",
            "kind": "event"
        },
        "action": {
            "name": "denied",
            "target": "network-traffic"
        },
        "cisco": {
            "ftd": {
                "icmp_code": "0",
                "icmp_type": "136"
            }
        },
        "network": {
            "transport": "ipv6-icmp"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "fe80::f037:5fbc:b824:230d",
            "address": "fe80::f037:5fbc:b824:230d"
        },
        "related": {
            "ip": [
                "fe80::f037:5fbc:b824:230d"
            ]
        }
    }
    	
	```


=== "test_ASA_716058.json"

    ```json
	
    {
        "message": "%ASA-6-716058: Group <CLIENT_VPN> User <Acme_account> IP <86.199.78.204> AnyConnect session lost connection. Waiting to resume.",
        "event": {
            "category": [
                "network"
            ],
            "code": "716058",
            "kind": "event"
        },
        "action": {
            "name": "anyconnect session lost connection",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "86.199.78.204",
            "address": "86.199.78.204"
        },
        "user": {
            "domain": "CLIENT_VPN",
            "name": "Acme_account"
        },
        "related": {
            "ip": [
                "86.199.78.204"
            ],
            "user": [
                "Acme_account"
            ]
        }
    }
    	
	```


=== "test_ASA_716059.json"

    ```json
	
    {
        "message": "%ASA-6-716059: Group <CLIENT_VPN> User <User_Acme> IP <10.17.100.175> AnyConnect session resumed connection from IP <10.17.100.175>.",
        "event": {
            "category": [
                "network"
            ],
            "code": "716059",
            "kind": "event"
        },
        "action": {
            "name": "anyconnect session resumed",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "10.17.100.175",
            "address": "10.17.100.175"
        },
        "user": {
            "domain": "CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "10.17.100.175"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722011.json"

    ```json
	
    {
        "message": "%ASA-5-722011: Group <GroupPolicy_CLIENT_VPN> User <User_acme> IP <91.172.139.4> SVC Message: 17/WARNING: Reconnecting the VPN tunnel..",
        "event": {
            "category": [
                "network"
            ],
            "code": "722011",
            "kind": "event"
        },
        "action": {
            "name": "reconnecting the vpn tunnel..",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "91.172.139.4",
            "address": "91.172.139.4"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_acme"
        },
        "related": {
            "ip": [
                "91.172.139.4"
            ],
            "user": [
                "User_acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722012.json"

    ```json
	
    {
        "message": "%ASA-5-722012: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <86.217.237.163> SVC Message: 16/NOTICE: Client PC is going into suspend mode (Sleep, Hibernate, etc)..",
        "event": {
            "category": [
                "network"
            ],
            "code": "722012",
            "kind": "event"
        },
        "action": {
            "name": "client pc is going into suspend mode (sleep, hibernate, etc)..",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "86.217.237.163",
            "address": "86.217.237.163"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "86.217.237.163"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722023.json"

    ```json
	
    {
        "message": "%ASA-6-722023: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <86.215.190.93> TCP SVC connection terminated without compression",
        "event": {
            "category": [
                "network"
            ],
            "code": "722023",
            "kind": "event"
        },
        "action": {
            "name": "svc connection terminated",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "86.215.190.93",
            "address": "86.215.190.93"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "86.215.190.93"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722028.json"

    ```json
	
    {
        "message": "%ASA-5-722028: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <91.172.139.4> Stale SVC connection closed.",
        "event": {
            "category": [
                "network"
            ],
            "code": "722028",
            "kind": "event"
        },
        "action": {
            "name": "connection closed.",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "91.172.139.4",
            "address": "91.172.139.4"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "91.172.139.4"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722032.json"

    ```json
	
    {
        "message": "%ASA-5-722032: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <93.23.18.76> New UDP SVC connection replacing old connection.",
        "event": {
            "category": [
                "network"
            ],
            "code": "722032",
            "kind": "event"
        },
        "action": {
            "name": "connection replacing old connection.",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "93.23.18.76",
            "address": "93.23.18.76"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "93.23.18.76"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722033.json"

    ```json
	
    {
        "message": "%ASA-5-722033: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <77.205.143.138> First TCP SVC connection established for SVC session.",
        "event": {
            "category": [
                "network"
            ],
            "code": "722033",
            "kind": "event"
        },
        "action": {
            "name": "connection established for svc session.",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "77.205.143.138",
            "address": "77.205.143.138"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "77.205.143.138"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722034.json"

    ```json
	
    {
        "message": "%ASA-5-722034: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <109.17.100.175> New TCP SVC connection, no existing connection.",
        "event": {
            "category": [
                "network"
            ],
            "code": "722034",
            "kind": "event"
        },
        "action": {
            "name": "connection, no existing connection.",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "109.17.100.175",
            "address": "109.17.100.175"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "109.17.100.175"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_722037.json"

    ```json
	
    {
        "message": "%ASA-4-722037: Group <GroupPolicy_CLIENT_VPN> User <User_Acme> IP <92.131.212.102> SVC closing connection: Transport closing.",
        "event": {
            "category": [
                "network"
            ],
            "code": "722037",
            "kind": "event"
        },
        "action": {
            "name": "closing connection",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "92.131.212.102",
            "address": "92.131.212.102"
        },
        "user": {
            "domain": "GroupPolicy_CLIENT_VPN",
            "name": "User_Acme"
        },
        "related": {
            "ip": [
                "92.131.212.102"
            ],
            "user": [
                "User_Acme"
            ]
        }
    }
    	
	```


=== "test_ASA_725001.json"

    ```json
	
    {
        "message": "%ASA-6-725001: Starting SSL handshake with client WAN:195.101.173.60/49238 for TLS session.",
        "event": {
            "category": [
                "network"
            ],
            "code": "725001",
            "kind": "event"
        },
        "action": {
            "name": "starting ssl handshake",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "195.101.173.60",
            "port": 49238,
            "address": "195.101.173.60"
        },
        "related": {
            "ip": [
                "195.101.173.60"
            ]
        }
    }
    	
	```


=== "test_ASA_725002.json"

    ```json
	
    {
        "message": "%ASA-6-725002: Device completed SSL handshake with client WAN:90.114.208.186/65531",
        "event": {
            "category": [
                "network"
            ],
            "code": "725002",
            "kind": "event"
        },
        "action": {
            "name": "device completed ssl handshake",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "90.114.208.186",
            "port": 6553,
            "address": "90.114.208.186"
        },
        "related": {
            "ip": [
                "90.114.208.186"
            ]
        }
    }
    	
	```


=== "test_ASA_725006.json"

    ```json
	
    {
        "message": "%ASA-6-725006: Device failed SSL handshake with client WAN:195.101.173.60/49699",
        "event": {
            "category": [
                "network"
            ],
            "code": "725006",
            "kind": "event"
        },
        "action": {
            "name": "device failed ssl handshake",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "195.101.173.60",
            "port": 4969,
            "address": "195.101.173.60"
        },
        "related": {
            "ip": [
                "195.101.173.60"
            ]
        }
    }
    	
	```


=== "test_ASA_725007.json"

    ```json
	
    {
        "message": "%ASA-6-725007: SSL session with client WAN:195.101.173.60/49486 terminated.",
        "event": {
            "category": [
                "network"
            ],
            "code": "725007",
            "kind": "event"
        },
        "action": {
            "name": "ssl session",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "195.101.173.60",
            "port": 49486,
            "address": "195.101.173.60"
        },
        "related": {
            "ip": [
                "195.101.173.60"
            ]
        }
    }
    	
	```


=== "test_ASA_733100.json"

    ```json
	
    {
        "message": "%ASA-4-733100: [scanning] drop rate-1 exceeded. Current burst rate is 8 per second, max configured rate is 10; Current average rate is 23 per second, max configured rate is 5; Cumulative total count is 14188",
        "event": {
            "category": [
                "network"
            ],
            "code": "733100",
            "kind": "event"
        },
        "action": {
            "name": "scanning",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        }
    }
    	
	```


=== "test_ASA_737016.json"

    ```json
	
    {
        "message": "%ASA-6-737016: IPAA: Freeing local pool address 192.168.122.247",
        "event": {
            "category": [
                "network"
            ],
            "code": "737016",
            "kind": "event"
        },
        "action": {
            "name": "freeing local pool address",
            "target": "network-traffic"
        },
        "observer": {
            "vendor": "Cisco",
            "product": "Adaptive Security Appliance"
        },
        "source": {
            "ip": "192.168.122.247",
            "address": "192.168.122.247"
        },
        "related": {
            "ip": [
                "192.168.122.247"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`action.target` | `keyword` | The target of the action. This field is mandatory for STIX2 compliance |
|`cisco.ftd.file_sandbox_status` | `keyword` | The descriptive name for the filelog sandbox status. |
|`cisco.ftd.file_storage_status` | `keyword` | The storage status of the file associated with the event |
|`cisco.ftd.icmp_code` | `keyword` | The ICMP code used by the session responder. |
|`cisco.ftd.icmp_type` | `keyword` | The ICMP type used by the session initiator. |
|`cisco.ftd.sha_disposition` | `keyword` | Sha disposition |
|`cisco.ftd.spero_disposition` | `keyword` |  The descriptive name for the filelog spero status. |
|`destination.bytes` | `long` | Bytes sent from the destination to the source. |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.nat.ip` | `ip` | Destination NAT ip |
|`destination.nat.port` | `long` | Destination NAT Port |
|`destination.packets` | `long` | Packets sent from the destination to the source. |
|`destination.port` | `long` | Port of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.extension` | `keyword` | File extension, excluding the leading dot. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.size` | `long` | File size in bytes. |
|`host.hostname` | `keyword` | Hostname of the host. |
|`host.ip` | `ip` | Host ip addresses. |
|`host.name` | `keyword` | Name of the host. |
|`http.request.bytes` | `long` | Total size in bytes of the request (body and headers). |
|`http.request.method` | `keyword` | HTTP request method. |
|`http.request.mime_type` | `keyword` | Mime type of the body of the request. |
|`http.response.bytes` | `long` | Total size in bytes of the response (body and headers). |
|`http.response.status_code` | `long` | HTTP response status code. |
|`log.level` | `keyword` | Log level of the log event. |
|`network.application` | `keyword` | Application level protocol name. |
|`network.bytes` | `long` | Total bytes transferred in both directions. |
|`network.direction` | `keyword` | Direction of the network traffic. |
|`network.protocol` | `keyword` | Application protocol name. |
|`network.transport` | `keyword` | Protocol Name corresponding to the field `iana_number`. |
|`observer.hostname` | `keyword` | Hostname of the observer. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`process.name` | `keyword` | Process name. |
|`rule.category` | `keyword` | Rule category |
|`rule.name` | `keyword` | Rule name |
|`rule.ruleset` | `keyword` | Rule ruleset |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.ip` | `ip` | IP address of the source. |
|`source.nat.ip` | `ip` | Source NAT ip |
|`source.nat.port` | `long` | Source NAT port |
|`source.packets` | `long` | Packets sent from the source to the destination. |
|`source.port` | `long` | Port of the source. |
|`threat.software.name` | `keyword` | Name of the software. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`url.path` | `wildcard` | Path of the request, such as "/search". |
|`url.scheme` | `keyword` | Scheme of the url. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

