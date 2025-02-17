
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `DNS records` | BIND provides detailed logs on handled DNS queries |








## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "query_log.json"

    ```json
	
    {
        "message": "client @0x7f62b80115d0 192.168.101.70#55575 (docs.sekoia.io): query: docs.sekoia.io IN AAAA + (192.168.100.102)",
        "source": {
            "address": "192.168.101.70",
            "ip": "192.168.101.70",
            "port": 55575
        },
        "related": {
            "ip": [
                "192.168.101.70"
            ]
        },
        "dns": {
            "question": {
                "class": "IN",
                "type": "AAAA",
                "name": "docs.sekoia.io",
                "top_level_domain": "io",
                "subdomain": "docs",
                "registered_domain": "sekoia.io"
            },
            "type": "query",
            "header_flags": [
                "RD"
            ]
        }
    }
    	
	```


=== "query_log_cd.json"

    ```json
	
    {
        "message": "client 192.168.101.70#55575 (docs.sekoia.io): query: docs.sekoia.io IN AAAA +TC (192.168.100.102)",
        "source": {
            "address": "192.168.101.70",
            "ip": "192.168.101.70",
            "port": 55575
        },
        "related": {
            "ip": [
                "192.168.101.70"
            ]
        },
        "dns": {
            "type": "query",
            "question": {
                "class": "IN",
                "type": "AAAA",
                "name": "docs.sekoia.io",
                "top_level_domain": "io",
                "subdomain": "docs",
                "registered_domain": "sekoia.io"
            },
            "header_flags": [
                "RD",
                "CD"
            ]
        },
        "network": {
            "transport": "tcp"
        }
    }
    	
	```


=== "query_log_dnssec.json"

    ```json
	
    {
        "message": "client 192.168.103.66#42811 (ipv6.google.com): query: ipv6.google.com IN A +EDC (192.168.100.102)",
        "source": {
            "address": "192.168.103.66",
            "ip": "192.168.103.66",
            "port": 42811
        },
        "related": {
            "ip": [
                "192.168.103.66"
            ]
        },
        "dns": {
            "type": "query",
            "question": {
                "class": "IN",
                "type": "A",
                "name": "ipv6.google.com",
                "top_level_domain": "com",
                "subdomain": "ipv6",
                "registered_domain": "google.com"
            },
            "header_flags": [
                "RD",
                "CD"
            ]
        }
    }
    	
	```


=== "query_log_edns_version.json"

    ```json
	
    {
        "message": "client @0x7f4f8003d9e0 192.168.101.61#38251 (global.vortex.data.trafficmanager.net): query: global.vortex.data.trafficmanager.net IN AAAA +E(0) (192.168.100.102)",
        "source": {
            "address": "192.168.101.61",
            "ip": "192.168.101.61",
            "port": 38251
        },
        "related": {
            "ip": [
                "192.168.101.61"
            ]
        },
        "dns": {
            "type": "query",
            "question": {
                "class": "IN",
                "type": "AAAA",
                "name": "global.vortex.data.trafficmanager.net",
                "top_level_domain": "net",
                "subdomain": "global.vortex.data",
                "registered_domain": "trafficmanager.net"
            },
            "header_flags": [
                "RD"
            ]
        }
    }
    	
	```


=== "query_log_no_recursion.json"

    ```json
	
    {
        "message": "client 192.168.103.66#57980 (ipv6.google.com): query: ipv6.google.com IN AAAA - (192.168.100.102)",
        "source": {
            "ip": "192.168.103.66",
            "port": 57980,
            "address": "192.168.103.66"
        },
        "dns": {
            "question": {
                "class": "IN",
                "type": "AAAA",
                "name": "ipv6.google.com",
                "top_level_domain": "com",
                "subdomain": "ipv6",
                "registered_domain": "google.com"
            },
            "type": "query",
            "header_flags": []
        },
        "related": {
            "ip": [
                "192.168.103.66"
            ]
        }
    }
    	
	```


=== "query_log_reverse.json"

    ```json
	
    {
        "message": "client 192.168.103.66#45041 (107.100.168.192.in-addr.arpa): query: 107.100.168.192.in-addr.arpa IN PTR +E (192.168.100.102)",
        "source": {
            "address": "192.168.103.66",
            "ip": "192.168.103.66",
            "port": 45041
        },
        "related": {
            "ip": [
                "192.168.103.66"
            ]
        },
        "dns": {
            "type": "query",
            "question": {
                "class": "IN",
                "type": "PTR",
                "name": "107.100.168.192.in-addr.arpa",
                "top_level_domain": "in-addr.arpa",
                "subdomain": "107.100.168",
                "registered_domain": "192.in-addr.arpa"
            },
            "header_flags": [
                "RD"
            ]
        }
    }
    	
	```


=== "query_log_tcp.json"

    ```json
	
    {
        "message": "client 192.168.101.70#55575 (docs.sekoia.io): query: docs.sekoia.io IN AAAA +ET (192.168.100.102)",
        "source": {
            "address": "192.168.101.70",
            "ip": "192.168.101.70",
            "port": 55575
        },
        "related": {
            "ip": [
                "192.168.101.70"
            ]
        },
        "dns": {
            "type": "query",
            "question": {
                "class": "IN",
                "type": "AAAA",
                "name": "docs.sekoia.io",
                "top_level_domain": "io",
                "subdomain": "docs",
                "registered_domain": "sekoia.io"
            },
            "header_flags": [
                "RD"
            ]
        },
        "network": {
            "transport": "tcp"
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`dns.header_flags` | `keyword` | Array of DNS header flags. |
|`dns.question.class` | `keyword` | The class of records being queried. |
|`dns.question.name` | `keyword` | The name being queried. |
|`dns.question.type` | `keyword` | The type of record being queried. |
|`dns.type` | `keyword` | The type of DNS event captured, query or answer. |
|`network.transport` | `keyword` | Protocol Name corresponding to the field `iana_number`. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |

