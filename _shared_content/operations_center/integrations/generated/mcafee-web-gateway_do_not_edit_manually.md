
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Anti-virus` | McAfee Web Gateway / Skyhigh Secure Web Gateway analyze the content of requests and responses to prevent malware infection |
| `Web proxy` | McAfee Web Gateway / Skyhigh Secure Web Gateway logs provide information about the connected client and the requested resource |
| `Web logs` | McAfee Web Gateway / Skyhigh Secure Web Gateway logs provide information about the connected client and the requested resource |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `network` |
| Type | `access`, `allowed`, `connection`, `denied` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "mcafee_access_log_blocked.json"

    ```json
	
    {
        "message": "date=\"2022-03-11T10:39:16.390Z\" hostname=\"mwgproxy\" username=\"\" source_ip=1.2.3.4 destination_ip=2.2.2.41 destination_host=\"www.forbiddensite.com\" http_status_code=403 media_type=\"\" source_bytes=131 destination_bytes=0 http_request_first_line=\"GET http://www.forbiddensite.com/ HTTP/1.1\" url_categories=\"Pornography\" url_reputation_string=\"Minimal Risk\" url_reputation_code=-28 ruleset_name=\"Default\" rule_name=\"Block URLs Whose Category Is in Category Blocklist for Default Groups\" block_id=10 block_reason=\"Blocked by URL filtering\" body_infected=false virus_names=\"\" body_modified=false application_reputation=\"Unverified\" application_name=\"forbiddenapp\" http_referer=\"\" user_agent=\"curl/7.77.0\"",
        "event": {
            "start": "2022-03-11T10:39:16.390000Z",
            "category": [
                "network"
            ],
            "code": "10",
            "kind": "event",
            "reason": "Blocked by URL filtering"
        },
        "destination": {
            "ip": "2.2.2.41",
            "domain": "www.forbiddensite.com",
            "address": "www.forbiddensite.com",
            "top_level_domain": "com",
            "subdomain": "www",
            "registered_domain": "forbiddensite.com"
        },
        "http": {
            "request": {
                "method": "GET",
                "bytes": 131
            },
            "response": {
                "bytes": 0,
                "status_code": 403
            }
        },
        "observer": {
            "hostname": "mwgproxy",
            "type": "proxy",
            "vendor": "McAfee Corp.",
            "product": "McAfee Web Gateway"
        },
        "rule": {
            "ruleset": "Default",
            "name": "Block URLs Whose Category Is in Category Blocklist for Default Groups"
        },
        "network": {
            "direction": "egress"
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "user_agent": {
            "original": "curl/7.77.0"
        },
        "url": {
            "original": "http://www.forbiddensite.com/",
            "domain": "www.forbiddensite.com",
            "top_level_domain": "com",
            "subdomain": "www",
            "registered_domain": "forbiddensite.com",
            "scheme": "http",
            "path": "/",
            "port": 80
        },
        "skyhighsecurity": {
            "application": {
                "reputation": "Unverified",
                "name": "forbiddenapp"
            },
            "url": {
                "reputation": "Minimal Risk",
                "reputation_code": -28,
                "categories": [
                    "Pornography"
                ]
            },
            "http": {
                "body": {
                    "infected": "false",
                    "modified": "false"
                }
            }
        },
        "related": {
            "hosts": [
                "mwgproxy",
                "www.forbiddensite.com"
            ],
            "ip": [
                "1.2.3.4",
                "2.2.2.41"
            ]
        }
    }
    	
	```


=== "mcafee_access_log_blocked2.json"

    ```json
	
    {
        "message": "date=\"2022-03-17T13:14:39.134Z\" hostname=\"mwgproxy\" username=\"\" source_ip=1.2.3.4 destination_ip=2.2.2.2 destination_host=\"slscr.update.microsoft.com\" http_status_code=407 media_type=\"\" source_bytes=173 destination_bytes=0 http_request_first_line=\"CONNECT slscr.update.microsoft.com:443 HTTP/1.1\" url_categories=\"Business, Software/Hardware\" url_reputation_string=\"Minimal Risk\" url_reputation_code=-42 ruleset_name=\"Authentication: Direct Proxy\" rule_name=\"Authenticate: Active Directory\" block_id=81 block_reason=\"Authentication Required\" body_infected=false virus_names=\"\" body_modified=false application_reputation=\"Unverified\" application_name=\"\" http_referer=\"\" user_agent=\"\"",
        "event": {
            "start": "2022-03-17T13:14:39.134000Z",
            "category": [
                "network"
            ],
            "code": "81",
            "kind": "event",
            "reason": "Authentication Required"
        },
        "destination": {
            "ip": "2.2.2.2",
            "domain": "slscr.update.microsoft.com",
            "port": 443,
            "address": "slscr.update.microsoft.com",
            "top_level_domain": "com",
            "subdomain": "slscr.update",
            "registered_domain": "microsoft.com"
        },
        "http": {
            "request": {
                "method": "CONNECT",
                "bytes": 173
            },
            "response": {
                "bytes": 0,
                "status_code": 407
            }
        },
        "observer": {
            "hostname": "mwgproxy",
            "type": "proxy",
            "vendor": "McAfee Corp.",
            "product": "McAfee Web Gateway"
        },
        "rule": {
            "ruleset": "Authentication: Direct Proxy",
            "name": "Authenticate: Active Directory"
        },
        "network": {
            "direction": "egress"
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "url": {
            "domain": "slscr.update.microsoft.com",
            "port": 443,
            "top_level_domain": "com",
            "subdomain": "slscr.update",
            "registered_domain": "microsoft.com"
        },
        "skyhighsecurity": {
            "application": {
                "reputation": "Unverified"
            },
            "url": {
                "reputation": "Minimal Risk",
                "reputation_code": -42,
                "categories": [
                    "Business",
                    "Software/Hardware"
                ]
            },
            "http": {
                "body": {
                    "infected": "false",
                    "modified": "false"
                }
            }
        },
        "related": {
            "hosts": [
                "mwgproxy",
                "slscr.update.microsoft.com"
            ],
            "ip": [
                "1.2.3.4",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "mcafee_access_log_empty_destination_host.json"

    ```json
	
    {
        "message": "date=\"2022-03-24T13:54:02.740Z\" hostname=\"mwgproxy\" username=\"myusername\" source_ip=1.2.3.4 destination_ip=255.255.255.255 destination_host=\"\" http_status_code=400 media_type=\"\" source_bytes=316 destination_bytes=0 http_request_first_line=\"CONNECT :80 HTTP/1.1\" url_categories=\"Business, Software/Hardware\" url_reputation_string=\"Minimal Risk\" url_reputation_code=-3 ruleset_name=\"Exception DFS\" rule_name=\"Forbidden Access\" block_id=10 block_reason=\"Blocked by URL filtering\" body_infected=false virus_names=\"\" body_modified=false application_reputation=\"Unverified\" application_name=\"\" http_referer=\"\" user_agent=\"\"",
        "event": {
            "start": "2022-03-24T13:54:02.740000Z",
            "category": [
                "network"
            ],
            "code": "10",
            "kind": "event",
            "reason": "Blocked by URL filtering"
        },
        "destination": {
            "ip": "255.255.255.255",
            "address": "255.255.255.255"
        },
        "http": {
            "request": {
                "method": "CONNECT",
                "bytes": 316
            },
            "response": {
                "bytes": 0,
                "status_code": 400
            }
        },
        "observer": {
            "hostname": "mwgproxy",
            "type": "proxy",
            "vendor": "McAfee Corp.",
            "product": "McAfee Web Gateway"
        },
        "rule": {
            "ruleset": "Exception DFS",
            "name": "Forbidden Access"
        },
        "network": {
            "direction": "egress"
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "user": {
            "name": "myusername"
        },
        "skyhighsecurity": {
            "application": {
                "reputation": "Unverified"
            },
            "url": {
                "reputation": "Minimal Risk",
                "reputation_code": -3,
                "categories": [
                    "Business",
                    "Software/Hardware"
                ]
            },
            "http": {
                "body": {
                    "infected": "false",
                    "modified": "false"
                }
            }
        },
        "related": {
            "hosts": [
                "mwgproxy"
            ],
            "ip": [
                "1.2.3.4",
                "255.255.255.255"
            ],
            "user": [
                "myusername"
            ]
        }
    }
    	
	```


=== "mcafee_access_log_success.json"

    ```json
	
    {
        "message": "date=\"2022-03-11T09:50:47.399Z\" hostname=\"mwgproxy\" username=\"myusername\" source_ip=1.2.3.4 destination_ip=142.250.178.131 destination_host=\"www.google.fr\" http_status_code=200 media_type=\"\" source_bytes=127 destination_bytes=14678 http_request_first_line=\"GET http://www.google.fr/ HTTP/1.1\" url_categories=\"Search Engines\" url_reputation_string=\"Minimal Risk\" url_reputation_code=0 ruleset_name=\"Dynamic Content Classification\" rule_name=\"Block URLs Whose Category Is in Category Blocklist\" block_id=0 block_reason=\"\" body_infected=false virus_names=\"\" body_modified=false application_reputation=\"Unverified\" application_name=\"\" http_referer=\"\" user_agent=\"curl/7.77.0\"",
        "event": {
            "start": "2022-03-11T09:50:47.399000Z",
            "category": [
                "network"
            ],
            "code": "0",
            "kind": "event",
            "action": "allowed",
            "type": [
                "connection",
                "access",
                "allowed"
            ]
        },
        "destination": {
            "ip": "142.250.178.131",
            "domain": "www.google.fr",
            "address": "www.google.fr",
            "top_level_domain": "fr",
            "subdomain": "www",
            "registered_domain": "google.fr"
        },
        "http": {
            "request": {
                "method": "GET",
                "bytes": 127
            },
            "response": {
                "bytes": 14678,
                "status_code": 200
            }
        },
        "observer": {
            "hostname": "mwgproxy",
            "type": "proxy",
            "vendor": "McAfee Corp.",
            "product": "McAfee Web Gateway"
        },
        "rule": {
            "ruleset": "Dynamic Content Classification",
            "name": "Block URLs Whose Category Is in Category Blocklist"
        },
        "network": {
            "direction": "egress"
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "user_agent": {
            "original": "curl/7.77.0"
        },
        "url": {
            "original": "http://www.google.fr/",
            "domain": "www.google.fr",
            "top_level_domain": "fr",
            "subdomain": "www",
            "registered_domain": "google.fr",
            "scheme": "http",
            "path": "/",
            "port": 80
        },
        "user": {
            "name": "myusername"
        },
        "skyhighsecurity": {
            "application": {
                "reputation": "Unverified"
            },
            "url": {
                "reputation": "Minimal Risk",
                "reputation_code": 0,
                "categories": [
                    "Search Engines"
                ]
            },
            "http": {
                "body": {
                    "infected": "false",
                    "modified": "false"
                }
            }
        },
        "related": {
            "hosts": [
                "mwgproxy",
                "www.google.fr"
            ],
            "ip": [
                "1.2.3.4",
                "142.250.178.131"
            ],
            "user": [
                "myusername"
            ]
        }
    }
    	
	```


=== "skyhigh_swg.json"

    ```json
	
    {
        "message": "user_id=-1 username=foo source_ip=37.171.139.5 http_action=CERTVERIFY server_to_client_bytes=0 client_to_server_bytes=0 requested_host=ping-edge.smartscreen.microsoft.com requested_path=/ result=OBSERVED virus= request_timestamp_epoch=1661260270 request_timestamp=2022-08-23 13:11:10 uri_scheme=https category=Business, Software/Hardware media_type=application/x-empty application_type= reputation=Minimal Risk last_rule=Allow http_status_code=200 client_ip=10.0.2.15 location= block_reason= user_agent_product=Other user_agent_version= user_agent_comment= process_name=msedge.exe destination_ip=20.108.130.238 destination_port=443 pop_country_code=FR referer= ssl_scanned=t av_scanned_up=t av_scanned_down=f rbi=f dlp=f client_system_name=desktop-rles2a6 filename= pop_egress_ip=161.69.108.44 pop_ingress_ip=10.42.47.222 proxy_port=8080",
        "event": {
            "category": [
                "network"
            ],
            "kind": "event",
            "action": "allowed",
            "type": [
                "connection",
                "access",
                "allowed"
            ]
        },
        "@timestamp": "2022-08-23T13:11:10.000000Z",
        "source": {
            "bytes": 0,
            "nat": {
                "ip": "37.171.139.5"
            },
            "ip": "10.0.2.15",
            "address": "10.0.2.15"
        },
        "destination": {
            "ip": "20.108.130.238",
            "domain": "ping-edge.smartscreen.microsoft.com",
            "bytes": 0,
            "port": 443,
            "address": "ping-edge.smartscreen.microsoft.com",
            "top_level_domain": "com",
            "subdomain": "ping-edge.smartscreen",
            "registered_domain": "microsoft.com"
        },
        "http": {
            "response": {
                "status_code": 200,
                "mime_type": "application/x-empty"
            },
            "request": {
                "mime_type": "application/x-empty"
            }
        },
        "url": {
            "scheme": "https",
            "path": "/"
        },
        "host": {
            "name": "desktop-rles2a6"
        },
        "process": {
            "name": "msedge.exe"
        },
        "observer": {
            "type": "proxy",
            "vendor": "McAfee Corp.",
            "product": "McAfee Web Gateway"
        },
        "rule": {
            "name": "Allow",
            "category": "Business, Software/Hardware"
        },
        "network": {
            "direction": "egress"
        },
        "user": {
            "name": "foo"
        },
        "skyhighsecurity": {
            "dlp": "f",
            "rbi": "f",
            "av_scanned_down": "f",
            "reputation": "Minimal Risk"
        },
        "related": {
            "hosts": [
                "ping-edge.smartscreen.microsoft.com"
            ],
            "ip": [
                "10.0.2.15",
                "20.108.130.238",
                "37.171.139.5"
            ],
            "user": [
                "foo"
            ]
        }
    }
    	
	```


=== "skyhigh_swg_block.json"

    ```json
	
    {
        "message": "id=-1 username=autorite nt\\\\service r\u00c9seau source_ip=1.1.1.1 http_action=GET server_to_client_bytes=3160 client_to_server_bytes=1137 requested_host=ctldl.windowsupdate.com requested_path=/msdownload/update/v3/static/trustedr/en/pinrulesstl.cab result=DENIED virus= request_timestamp_epoch=1661266553 request_timestamp=2022-08-23 14:55:53 uri_scheme=http category=Software/Hardware media_type= application_type= reputation=Minimal Risk last_rule=Block if MCP Authentication Failed http_status_code=403 client_ip=1.1.1.1 location= block_reason=Authentication Required user_agent_product=Other user_agent_version= user_agent_comment= process_name=svchost.exe destination_ip=1.1.1.1 destination_port=80 pop_country_code=fr referer= ssl_scanned=f av_scanned_up=f av_scanned_down=f rbi=f dlp=f client_system_name= filename=pinrulesstl.cab pop_egress_ip=1.1.1.1pop_ingress_ip=1.1.1.1 proxy_port=80",
        "event": {
            "category": [
                "network"
            ],
            "kind": "event",
            "action": "denied",
            "reason": "Authentication Required",
            "type": [
                "connection",
                "access",
                "denied"
            ]
        },
        "@timestamp": "2022-08-23T14:55:53.000000Z",
        "source": {
            "bytes": 1137,
            "nat": {
                "ip": "1.1.1.1"
            },
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "destination": {
            "ip": "1.1.1.1",
            "domain": "ctldl.windowsupdate.com",
            "bytes": 3160,
            "port": 80,
            "address": "ctldl.windowsupdate.com",
            "top_level_domain": "com",
            "subdomain": "ctldl",
            "registered_domain": "windowsupdate.com"
        },
        "http": {
            "response": {
                "status_code": 403
            }
        },
        "url": {
            "scheme": "http",
            "path": "/msdownload/update/v3/static/trustedr/en/pinrulesstl.cab"
        },
        "process": {
            "name": "svchost.exe"
        },
        "observer": {
            "type": "proxy",
            "vendor": "McAfee Corp.",
            "product": "McAfee Web Gateway"
        },
        "file": {
            "name": "pinrulesstl.cab"
        },
        "rule": {
            "name": "Block if MCP Authentication Failed",
            "category": "Software/Hardware"
        },
        "network": {
            "direction": "egress"
        },
        "user": {
            "name": "autorite nt\\\\service r\u00c9seau"
        },
        "skyhighsecurity": {
            "dlp": "f",
            "rbi": "f",
            "av_scanned_down": "f",
            "reputation": "Minimal Risk"
        },
        "related": {
            "hosts": [
                "ctldl.windowsupdate.com"
            ],
            "ip": [
                "1.1.1.1"
            ],
            "user": [
                "autorite nt\\\\service r\u00c9seau"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`destination.bytes` | `long` | Bytes sent from the destination to the source. |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`host.name` | `keyword` | Name of the host. |
|`http.request.bytes` | `long` | Total size in bytes of the request (body and headers). |
|`http.request.method` | `keyword` | HTTP request method. |
|`http.request.mime_type` | `keyword` | Mime type of the body of the request. |
|`http.request.referrer` | `keyword` | Referrer for this HTTP request. |
|`http.response.bytes` | `long` | Total size in bytes of the response (body and headers). |
|`http.response.mime_type` | `keyword` | Mime type of the body of the response. |
|`http.response.status_code` | `long` | HTTP response status code. |
|`network.direction` | `keyword` | Direction of the network traffic. |
|`observer.hostname` | `keyword` | Hostname of the observer. |
|`observer.product` | `keyword` | The product name of the observer. |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`process.name` | `keyword` | Process name. |
|`rule.category` | `keyword` | Rule category |
|`rule.name` | `keyword` | Rule name |
|`rule.ruleset` | `keyword` | Rule ruleset |
|`skyhighsecurity.application.name` | `keyword` | The name of the web application requested |
|`skyhighsecurity.application.reputation` | `keyword` | The reputation string of the web application requested |
|`skyhighsecurity.http.body.infected` | `keyword` | Flag to indicate if the body was infected |
|`skyhighsecurity.http.body.modified` | `keyword` | Flag to indicate if the body was modified (due to infection) |
|`skyhighsecurity.url.categories` | `text` | The list of categories associated to the url |
|`skyhighsecurity.url.reputation` | `keyword` | The reputation string of an url |
|`skyhighsecurity.url.reputation_code` | `number` | The reputation code of an url |
|`skyhighsecurity.viruses` | `text` | A list of virus name |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.ip` | `ip` | IP address of the source. |
|`source.nat.ip` | `ip` | Source NAT ip |
|`url.domain` | `keyword` | Domain of the url. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`url.path` | `wildcard` | Path of the request, such as "/search". |
|`url.port` | `long` | Port of the request, such as 443. |
|`url.scheme` | `keyword` | Scheme of the url. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

