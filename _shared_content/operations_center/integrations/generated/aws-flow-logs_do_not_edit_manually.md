
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Host network interface` | every packets passing through the AWS account are logged |
| `Netflow/Enclave netflow` | AWS Flow Logs are Netflow-like |
| `Network device logs` | packets logged by Flow Logs |
| `Network protocol analysis` | traffic analysis at levels 2/3/4 |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `["network"]` |
| Type | `` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "accept.json"

    ```json
	
    {
        "message": "2 424805057484 eni-0f06a40fc9be596f6 212.83.179.156 10.0.0.96 123 123 17 2 152 1599665193 1599665488 ACCEPT OK",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2020-09-09T15:26:33.000000Z",
            "end": "2020-09-09T15:31:28.000000Z",
            "action": "accept",
            "type": [
                "allowed"
            ]
        },
        "action": {
            "outcome": "ok",
            "type": "forward",
            "name": "accept",
            "target": "network-traffic"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "424805057484"
            }
        },
        "destination": {
            "ip": "10.0.0.96",
            "port": 123,
            "address": "10.0.0.96"
        },
        "network": {
            "iana_number": "17",
            "transport": "udp"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-0f06a40fc9be596f6"
                }
            }
        },
        "source": {
            "ip": "212.83.179.156",
            "port": 123,
            "bytes": 152,
            "packets": 2,
            "address": "212.83.179.156"
        },
        "user": {
            "id": "424805057484"
        },
        "related": {
            "ip": [
                "10.0.0.96",
                "212.83.179.156"
            ]
        }
    }
    	
	```


=== "accept_structured.json"

    ```json
	
    {
        "message": "{\"version\":2,\"account_id\":\"424805057484\",\"interface_id\":\"eni-0f06a40fc9be596f6\",\"srcaddr\":\"5.6.7.8\",\"dstaddr\":\"1.2.3.4\",\"srcport\":4712,\"dstport\":53205,\"protocol\":6,\"packets\":12,\"bytes\":2610,\"start\":1661950735,\"end\":1661950746,\"action\":\"ACCEPT\",\"log_status\":\"OK\"}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2022-08-31T12:58:55.000000Z",
            "end": "2022-08-31T12:59:06.000000Z",
            "action": "accept",
            "type": [
                "allowed"
            ]
        },
        "action": {
            "outcome": "ok",
            "type": "forward",
            "name": "accept",
            "target": "network-traffic"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "424805057484"
            }
        },
        "destination": {
            "ip": "1.2.3.4",
            "port": 53205,
            "address": "1.2.3.4"
        },
        "network": {
            "iana_number": "6",
            "transport": "tcp"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-0f06a40fc9be596f6"
                }
            }
        },
        "source": {
            "ip": "5.6.7.8",
            "port": 4712,
            "bytes": 2610,
            "packets": 12,
            "address": "5.6.7.8"
        },
        "user": {
            "id": "424805057484"
        },
        "related": {
            "ip": [
                "1.2.3.4",
                "5.6.7.8"
            ]
        }
    }
    	
	```


=== "custom.json"

    ```json
	
    {
        "message": "5 424805057484 eni-1235b8ca123456789 52.95.128.179 10.0.0.71 46945 53 17 1 73 1658131186 1658131216 ACCEPT OK vpc-abcdefab012345678 subnet-aaaaaaaa012345678 - 0 IPv4 52.95.128.179 10.0.0.71 eu-west-1 euw1-az3 - - - - egress 8",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2022-07-18T07:59:46.000000Z",
            "end": "2022-07-18T08:00:16.000000Z",
            "action": "accept",
            "type": [
                "allowed"
            ]
        },
        "action": {
            "outcome": "ok",
            "type": "forward",
            "name": "accept",
            "target": "network-traffic"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "424805057484"
            }
        },
        "destination": {
            "ip": "10.0.0.71",
            "port": 53,
            "address": "10.0.0.71"
        },
        "network": {
            "iana_number": "17",
            "transport": "udp"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-1235b8ca123456789"
                }
            }
        },
        "source": {
            "ip": "52.95.128.179",
            "port": 46945,
            "bytes": 73,
            "packets": 1,
            "address": "52.95.128.179"
        },
        "user": {
            "id": "424805057484"
        },
        "related": {
            "ip": [
                "10.0.0.71",
                "52.95.128.179"
            ]
        }
    }
    	
	```


=== "ipv6traffic.json"

    ```json
	
    {
        "message": "2 123456789010 eni-1235b8ca123456789 2001:db8:1234:a100:8d6e:3477:df66:f105 2001:db8:1234:a102:3304:8879:34cf:4071 34892 22 6 54 8855 1477913708 1477913820 ACCEPT OK",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2016-10-31T11:35:08.000000Z",
            "end": "2016-10-31T11:37:00.000000Z",
            "action": "accept",
            "type": [
                "allowed"
            ]
        },
        "action": {
            "outcome": "ok",
            "type": "forward",
            "name": "accept",
            "target": "network-traffic"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "123456789010"
            }
        },
        "destination": {
            "ip": "2001:db8:1234:a102:3304:8879:34cf:4071",
            "port": 22,
            "address": "2001:db8:1234:a102:3304:8879:34cf:4071"
        },
        "network": {
            "iana_number": "6",
            "transport": "tcp"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-1235b8ca123456789"
                }
            }
        },
        "source": {
            "ip": "2001:db8:1234:a100:8d6e:3477:df66:f105",
            "port": 34892,
            "bytes": 8855,
            "packets": 54,
            "address": "2001:db8:1234:a100:8d6e:3477:df66:f105"
        },
        "user": {
            "id": "123456789010"
        },
        "related": {
            "ip": [
                "2001:db8:1234:a100:8d6e:3477:df66:f105",
                "2001:db8:1234:a102:3304:8879:34cf:4071"
            ]
        }
    }
    	
	```


=== "nodata.json"

    ```json
	
    {
        "message": "2 123456789010 eni-1235b8ca123456789 - - - - - - - 1431280876 1431280934 - NODATA",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2015-05-10T18:01:16.000000Z",
            "end": "2015-05-10T18:02:14.000000Z"
        },
        "action": {
            "outcome": "nodata",
            "type": "forward"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "123456789010"
            }
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-1235b8ca123456789"
                }
            }
        },
        "user": {
            "id": "123456789010"
        }
    }
    	
	```


=== "reject.json"

    ```json
	
    {
        "message": "2 424805057484 eni-0f06a40fc9be596f6 195.14.170.50 10.0.0.96 53996 20248 6 1 40 1599665374 1599665428 REJECT OK",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2020-09-09T15:29:34.000000Z",
            "end": "2020-09-09T15:30:28.000000Z",
            "action": "reject",
            "type": [
                "denied"
            ]
        },
        "action": {
            "outcome": "ok",
            "type": "forward",
            "name": "reject",
            "target": "network-traffic"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "424805057484"
            }
        },
        "destination": {
            "ip": "10.0.0.96",
            "port": 20248,
            "address": "10.0.0.96"
        },
        "network": {
            "iana_number": "6",
            "transport": "tcp"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-0f06a40fc9be596f6"
                }
            }
        },
        "source": {
            "ip": "195.14.170.50",
            "port": 53996,
            "bytes": 40,
            "packets": 1,
            "address": "195.14.170.50"
        },
        "user": {
            "id": "424805057484"
        },
        "related": {
            "ip": [
                "10.0.0.96",
                "195.14.170.50"
            ]
        }
    }
    	
	```


=== "reject_structured.json"

    ```json
	
    {
        "message": "{\"version\":2,\"account_id\":\"424805057484\",\"interface_id\":\"eni-0f06a40fc9be596f6\",\"srcaddr\":\"1.2.3.4\",\"dstaddr\":\"5.6.7.8\",\"srcport\":53094,\"dstport\":2323,\"protocol\":6,\"packets\":1,\"bytes\":40,\"start\":1661950735,\"end\":1661950746,\"action\":\"REJECT\",\"log_status\":\"OK\"}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "start": "2022-08-31T12:58:55.000000Z",
            "end": "2022-08-31T12:59:06.000000Z",
            "action": "reject",
            "type": [
                "denied"
            ]
        },
        "action": {
            "outcome": "ok",
            "type": "forward",
            "name": "reject",
            "target": "network-traffic"
        },
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "vpc"
            },
            "account": {
                "id": "424805057484"
            }
        },
        "destination": {
            "ip": "5.6.7.8",
            "port": 2323,
            "address": "5.6.7.8"
        },
        "network": {
            "iana_number": "6",
            "transport": "tcp"
        },
        "observer": {
            "ingress": {
                "interface": {
                    "name": "eni-0f06a40fc9be596f6"
                }
            }
        },
        "source": {
            "ip": "1.2.3.4",
            "port": 53094,
            "bytes": 40,
            "packets": 1,
            "address": "1.2.3.4"
        },
        "user": {
            "id": "424805057484"
        },
        "related": {
            "ip": [
                "1.2.3.4",
                "5.6.7.8"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`action.name` | `keyword` | The name of the action |
|`action.outcome` | `keyword` | The outcome of the action |
|`action.target` | `keyword` | The target of the action |
|`action.type` | `keyword` | The type of the action |
|`cloud.account.id` | `keyword` | The cloud account or organization id. |
|`cloud.provider` | `keyword` | Name of the cloud provider. |
|`cloud.service.name` | `keyword` | The cloud service name. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.end` | `date` | event.end contains the date when the event ended or when the activity was last observed. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`network.iana_number` | `keyword` | IANA Protocol Number. |
|`observer.ingress.interface.name` | `keyword` | Interface name |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.ip` | `ip` | IP address of the source. |
|`source.packets` | `long` | Packets sent from the source to the destination. |
|`source.port` | `long` | Port of the source. |
|`user.id` | `keyword` | Unique identifier of the user. |

