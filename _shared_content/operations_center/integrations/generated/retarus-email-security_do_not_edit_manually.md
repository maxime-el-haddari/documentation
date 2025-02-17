
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Email gateway` | Retarus Email Security solution. |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `alert`, `event` |
| Category | `malware`, `web` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "event.json"

    ```json
	
    {
        "message": "{\"direction\": \"OUTBOUND\", \"class\": \"EVENT\", \"version\": \"1.0\", \"type\": \"MTA\", \"ts\": \"2021-05-18 16:50:30 +0200\", \"host\": \"events.retarus.com\", \"customer\": \"45987FR\", \"metaData\": {}, \"sender\": \"utilisateur@mail.fr\", \"status\": \"ACCEPTED\", \"mimeId\": \"<d12b9brrfd3c89723ee5@STZE007.super.corp>\", \"rmxId\": \"20210518-32464-yvrfukcZEcd-0@out33.fg\", \"sourceIp\": \"255.255.255.1\", \"recipient\": \"recepient@mail.com\"}",
        "event": {
            "kind": "event"
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "45987FR"
        },
        "source": {
            "ip": "255.255.255.1",
            "domain": "mail.fr",
            "address": "mail.fr",
            "top_level_domain": "fr",
            "registered_domain": "mail.fr"
        },
        "destination": {
            "domain": "mail.com",
            "address": "mail.com",
            "top_level_domain": "com",
            "registered_domain": "mail.com"
        },
        "retarus": {
            "timestamp": "2021-05-18 16:50:30 +0200",
            "email_direction": "OUTBOUND",
            "mime_message_id": "<d12b9brrfd3c89723ee5@STZE007.super.corp>",
            "message_id": "20210518-32464-yvrfukcZEcd-0@out33.fg",
            "recipient": "recepient@mail.com",
            "sender": "utilisateur@mail.fr",
            "status": "ACCEPTED",
            "class": "EVENT",
            "type": "MTA"
        },
        "action": {
            "name": "EVENT",
            "outcome": "success",
            "outcome_reason": "ACCEPTED"
        },
        "related": {
            "hosts": [
                "events.retarus.com",
                "mail.com",
                "mail.fr"
            ],
            "ip": [
                "255.255.255.1"
            ]
        }
    }
    	
	```


=== "event_inbound.json"

    ```json
	
    {
        "action": {
            "name": "EVENT",
            "outcome": "success",
            "outcome_reason": "ACCEPTED"
        },
        "destination": {
            "address": "retarus.de",
            "domain": "retarus.de",
            "registered_domain": "retarus.de",
            "top_level_domain": "de"
        },
        "ecs": {
            "version": "1.10.0"
        },
        "event": {
            "kind": "event"
        },
        "message": "{\"customer\": \"CuNo\",\"metaData\": {\"authentication\": {\"dkim\": {\"status\": \"dkim=none\",\"details\": \"dkim=none reason=\\\"no signature\\\"\"}},\"transportEncryption\": {\"requested\": false,\"established\": false},\"header\": {\"subject\": \"This is a test mail\",\"from\": \"sender@example.com\"},\"contentEncryption\": false},\"host\": \"events.retarus.com\",\"ts\": \"2021-07-11 14:58:43 +0200\",\"version\": \"1.0\",\"sourceIp\": \"xxx.xxx.xxx.xxx\",\"sender\": \"xxxxxxx@retarus.com\",\"type\": \"MTA\",\"subtype\": \"INCOMING\",\"direction\": \"INBOUND\",\"recipient\": \"xxxxxxx@retarus.de\",\"mimeId\": \"<5616dfeid.xxxxxxxxxx@retarus.net>\",\"status\": \"ACCEPTED\",\"class\": \"EVENT\",\"rmxId\": \"20210711-145842-xxxxxx-xxxxxx-0@mailin27\"}",
        "observer": {
            "hostname": "events.retarus.com",
            "version": "1.0"
        },
        "organization": {
            "id": "CuNo"
        },
        "related": {
            "hosts": [
                "events.retarus.com",
                "retarus.com",
                "retarus.de"
            ],
            "ip": [
                "xxx.xxx.xxx.xxx"
            ]
        },
        "retarus": {
            "class": "EVENT",
            "email_direction": "INBOUND",
            "message_id": "20210711-145842-xxxxxx-xxxxxx-0@mailin27",
            "mime_message_id": "<5616dfeid.xxxxxxxxxx@retarus.net>",
            "recipient": "xxxxxxx@retarus.de",
            "sender": "xxxxxxx@retarus.com",
            "status": "ACCEPTED",
            "timestamp": "2021-07-11 14:58:43 +0200",
            "type": "MTA"
        },
        "sekoiaio": {
            "intake": {
                "dialect": "retarus-email-security",
                "dialect_uuid": "46fe3905-9e38-4fb2-be09-44d31626b694"
            }
        },
        "source": {
            "address": "retarus.com",
            "domain": "retarus.com",
            "ip": "xxx.xxx.xxx.xxx",
            "registered_domain": "retarus.com",
            "top_level_domain": "com"
        }
    }
    	
	```


=== "event_no_sender.json"

    ```json
	
    {
        "message": "{\"version\":\"1.0\",\"rmxId\":\"20220912-000000-111111111111-0@example\",\"sender\":\"\",\"ts\":\"2022-09-12 16:30:58 +0200\",\"metaData\":{\"transportEncryption\":{\"protocol\":\"TLSv1.2\",\"cipherSuite\":\"ECDHE-RSA-AES256-GCM-SHA384 (256/256 bits)\",\"established\":true,\"requested\":true},\"authentication\":{\"dkim\":{\"status\":\"dkim=none\",\"details\":\"dkim=none reason=\\\"no signature\\\"\"},\"spf\":{\"status\":\"spf=none\",\"details\":\"spf=none smtp.helo=mailer.com\"}},\"header\":{\"from\":\"MAILER-DAEMON (Mail Delivery System)\",\"subject\":\"Undelivered Mail Returned to Sender\"},\"contentEncryption\":false},\"recipient\":\"user@example.org\",\"sourceIp\":\"1.2.3.4\",\"type\":\"MTA\",\"subtype\":\"INCOMING\",\"host\":\"events.retarus.com\",\"direction\":\"INBOUND\",\"status\":\"ACCEPTED\",\"customer\":\"15752FR\",\"class\":\"EVENT\",\"mimeId\":\"<00000000@mailer.com>\"}\n",
        "event": {
            "kind": "event"
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "15752FR"
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "destination": {
            "domain": "example.org",
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "retarus": {
            "timestamp": "2022-09-12 16:30:58 +0200",
            "email_direction": "INBOUND",
            "mime_message_id": "<00000000@mailer.com>",
            "message_id": "20220912-000000-111111111111-0@example",
            "recipient": "user@example.org",
            "status": "ACCEPTED",
            "class": "EVENT",
            "type": "MTA"
        },
        "action": {
            "name": "EVENT",
            "outcome": "success",
            "outcome_reason": "ACCEPTED"
        },
        "related": {
            "hosts": [
                "events.retarus.com",
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_outbound.json"

    ```json
	
    {
        "message": "{\"customer\": \"CuNo\",\"metaData\": {\"transportEncryption\": {\"requested\": true,\"established\": true,\"protocol\": \"TLSv1.2\",\"cipherSuite\": \"ECDHE-RSA-AES128-SHA256(128/128bits)\"},\"header\": {\"subject\": \"This is a test mail\",\"from\": \"sender@example.com\"}},\"host\": \"events.retarus.com\",\"ts\": \"2021-07-11 14:58:43 +0200\",\"version\": \"1.0\",\"sourceIp\": \"255.255.255.1\",\"sender\": \"xxxxxxx@retarus.com\",\"type\": \"MTA\",\"subtype\": \"INCOMING\",\"direction\": \"OUTBOUND\",\"recipient\": \"xxxxxxx@retarus.de\",\"mimeId\": \"<5616dfeid.xxxxxxxxxx@retarus.net>\",\"status\": \"ACCEPTED\",\"class\": \"EVENT\",\"rmxId\": \"20210711-145842-xxxxxx-xxxxxx-0@mailin27\"}",
        "event": {
            "kind": "event"
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "CuNo"
        },
        "source": {
            "ip": "255.255.255.1",
            "domain": "retarus.com",
            "address": "retarus.com",
            "top_level_domain": "com",
            "registered_domain": "retarus.com"
        },
        "destination": {
            "domain": "retarus.de",
            "address": "retarus.de",
            "top_level_domain": "de",
            "registered_domain": "retarus.de"
        },
        "retarus": {
            "timestamp": "2021-07-11 14:58:43 +0200",
            "email_direction": "OUTBOUND",
            "mime_message_id": "<5616dfeid.xxxxxxxxxx@retarus.net>",
            "message_id": "20210711-145842-xxxxxx-xxxxxx-0@mailin27",
            "recipient": "xxxxxxx@retarus.de",
            "sender": "xxxxxxx@retarus.com",
            "status": "ACCEPTED",
            "class": "EVENT",
            "type": "MTA"
        },
        "action": {
            "name": "EVENT",
            "outcome": "success",
            "outcome_reason": "ACCEPTED"
        },
        "related": {
            "hosts": [
                "events.retarus.com",
                "retarus.com",
                "retarus.de"
            ],
            "ip": [
                "255.255.255.1"
            ]
        }
    }
    	
	```


=== "example1.json"

    ```json
	
    {
        "message": "{\"class\": \"EVENT\", \"rmxId\": \"0001\", \"sourceIp\": \"1.1.1.1\", \"metaData\": {\"header\": {\"from\": \"sender <sender@senderdomain.fr>\", \"subject\": \"This is a subject\"}, \"transportEncryption\": {\"requested\": true, \"established\": true, \"protocol\": \"TLSv1.2\", \"cipherSuite\": \"ecdhe-ecdsa-aes128-gcm-sha256\"}}, \"recipient\": \"recipient@recipientdomain.fr\", \"mimeId\": \"<11111111>\", \"sender\": \"sender@senderdomain.fr\", \"version\": \"1.0\", \"customer\": \"1\", \"host\": \"host.fr\", \"subtype\": \"INCOMING\", \"type\": \"AAA\", \"ts\": \"2021-10-1 09:00:00 +0200\", \"direction\": \"OUTBOUND\", \"status\": \"ACCEPTED\"}",
        "observer": {
            "version": "1.0",
            "hostname": "host.fr"
        },
        "organization": {
            "id": "1"
        },
        "source": {
            "ip": "1.1.1.1",
            "domain": "senderdomain.fr",
            "address": "senderdomain.fr",
            "top_level_domain": "fr",
            "registered_domain": "senderdomain.fr"
        },
        "destination": {
            "domain": "recipientdomain.fr",
            "address": "recipientdomain.fr",
            "top_level_domain": "fr",
            "registered_domain": "recipientdomain.fr"
        },
        "retarus": {
            "timestamp": "2021-10-1 09:00:00 +0200",
            "email_direction": "OUTBOUND",
            "mime_message_id": "<11111111>",
            "message_id": "0001",
            "recipient": "recipient@recipientdomain.fr",
            "sender": "sender@senderdomain.fr",
            "status": "ACCEPTED",
            "class": "EVENT",
            "type": "AAA"
        },
        "related": {
            "hosts": [
                "host.fr",
                "recipientdomain.fr",
                "senderdomain.fr"
            ],
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "threat_cx0.json"

    ```json
	
    {
        "message": "{\"customer\": \"CuNo\", \"metaData\": {}, \"host\": \"events.retarus.com\", \"ts\": \"2018-10-16 14:58:18 +0200\", \"version\": \"1.0\", \"sourceIp\": \"xxx.xxx.xxx.xxx\", \"sender\": \"xxxxxxx@retarus.com\", \"type\": \"CxO\", \"direction\": \"INBOUND\", \"recipient\": \"xxxxxxx@retarus.de\", \"mimeId\": \"<164D6G96.xxxxxxx@retarus.net>\", \"status\": \"DETECTED\", \"class\": \"THREAT\", \"rmxId\": \"20181016-145817-42ZFjPxxxxxx-0@mailin01\"}",
        "event": {
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ]
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "CuNo"
        },
        "source": {
            "ip": "xxx.xxx.xxx.xxx",
            "domain": "retarus.com",
            "address": "retarus.com",
            "top_level_domain": "com",
            "registered_domain": "retarus.com"
        },
        "destination": {
            "domain": "retarus.de",
            "address": "retarus.de",
            "top_level_domain": "de",
            "registered_domain": "retarus.de"
        },
        "retarus": {
            "timestamp": "2018-10-16 14:58:18 +0200",
            "email_direction": "INBOUND",
            "mime_message_id": "<164D6G96.xxxxxxx@retarus.net>",
            "message_id": "20181016-145817-42ZFjPxxxxxx-0@mailin01",
            "recipient": "xxxxxxx@retarus.de",
            "sender": "xxxxxxx@retarus.com",
            "status": "DETECTED",
            "class": "THREAT",
            "type": "CxO"
        },
        "action": {
            "name": "THREAT",
            "outcome": "failure"
        },
        "related": {
            "hosts": [
                "events.retarus.com",
                "retarus.com",
                "retarus.de"
            ],
            "ip": [
                "xxx.xxx.xxx.xxx"
            ]
        }
    }
    	
	```


=== "threat_multiscan.json"

    ```json
	
    {
        "message": "{\"customer\": \"CuNo\", \"metaData\": {\"details\": \"EICAR-AV-Test\"}, \"host\": \"events.retarus.com\", \"ts\": \"2018-10-16 14:58:43 +0200\", \"version\": \"1.0\", \"sourceIp\": \"xxx.xxx.xxx.xxx\", \"sender\": \"xxxxxxx@retarus.com\", \"type\": \"MultiScan\", \"direction\": \"OUTBOUND\", \"recipient\": \"xxxxxxx@retarus.de\", \"mimeId\": \"<5616dfeid.xxxxxxxxxx@retarus.net>\", \"status\": \"INFECTED\", \"class\": \"THREAT\", \"rmxId\": \"20181016-145842-xxxxxx-xxxxxx-0@mailin27\"}",
        "event": {
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ]
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "CuNo"
        },
        "source": {
            "ip": "xxx.xxx.xxx.xxx",
            "domain": "retarus.com",
            "address": "retarus.com",
            "top_level_domain": "com",
            "registered_domain": "retarus.com"
        },
        "destination": {
            "domain": "retarus.de",
            "address": "retarus.de",
            "top_level_domain": "de",
            "registered_domain": "retarus.de"
        },
        "retarus": {
            "timestamp": "2018-10-16 14:58:43 +0200",
            "email_direction": "OUTBOUND",
            "mime_message_id": "<5616dfeid.xxxxxxxxxx@retarus.net>",
            "message_id": "20181016-145842-xxxxxx-xxxxxx-0@mailin27",
            "recipient": "xxxxxxx@retarus.de",
            "sender": "xxxxxxx@retarus.com",
            "status": "INFECTED",
            "class": "THREAT",
            "type": "MultiScan",
            "virus_name": "EICAR-AV-Test"
        },
        "action": {
            "name": "THREAT",
            "outcome": "failure"
        },
        "related": {
            "hosts": [
                "events.retarus.com",
                "retarus.com",
                "retarus.de"
            ],
            "ip": [
                "xxx.xxx.xxx.xxx"
            ]
        }
    }
    	
	```


=== "threat_pzd.json"

    ```json
	
    {
        "message": "{\"customer\": \"CuNo\", \"metaData\": {\"hashFunction\": \"sha256\", \"threatType\": \"VIRUS\", \"checksum\": \"6b84714d0fa8c77d846306f37f4f3135596d34e17dca4f84088195272fd\", \"mimeType\": \"applicationx-dosexec\", \"details\": \"EICAR-Test-File\"}, \"host\": \"events.retarus.com\", \"ts\": \"2018-10-16 14:58:56 +0200\", \"version\": \"1.0\", \"sourceIp\": \"xxx.xxx.xxx.xxx\", \"sender\": \"xxxxxx@retarus.de\", \"type\": \"PZD\", \"direction\": \"INBOUND\", \"recipient\": \"xxxxxxx@retarus.de\", \"mimeId\": \"<56168B42.xxxxxxx@retarus.net>\", \"status\": \"DETECTED\", \"class\": \"THREAT\", \"rmxId\": \"20181016-145852-xxxxxx-xxxxxx-0@mailin01\"}",
        "event": {
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ]
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "CuNo"
        },
        "source": {
            "ip": "xxx.xxx.xxx.xxx",
            "domain": "retarus.de",
            "address": "retarus.de",
            "top_level_domain": "de",
            "registered_domain": "retarus.de"
        },
        "destination": {
            "domain": "retarus.de",
            "address": "retarus.de",
            "top_level_domain": "de",
            "registered_domain": "retarus.de"
        },
        "retarus": {
            "timestamp": "2018-10-16 14:58:56 +0200",
            "email_direction": "INBOUND",
            "mime_message_id": "<56168B42.xxxxxxx@retarus.net>",
            "message_id": "20181016-145852-xxxxxx-xxxxxx-0@mailin01",
            "recipient": "xxxxxxx@retarus.de",
            "sender": "xxxxxx@retarus.de",
            "status": "DETECTED",
            "class": "THREAT",
            "type": "PZD",
            "virus_name": "EICAR-Test-File"
        },
        "action": {
            "name": "THREAT",
            "outcome": "failure"
        },
        "file": {
            "mimeType": "applicationx-dosexec",
            "hash": {
                "sha256": "sha256"
            }
        },
        "related": {
            "hash": [
                "sha256"
            ],
            "hosts": [
                "events.retarus.com",
                "retarus.de"
            ],
            "ip": [
                "xxx.xxx.xxx.xxx"
            ]
        }
    }
    	
	```


=== "threat_sandboxing.json"

    ```json
	
    {
        "message": "{\"customer\": \"CuNo\", \"metaData\": {\"hashFunction\": \"sha256\", \"checksum\": \"cbfdedf25f7f04daf9d705548cf6b6546d66bc206ea1a166fff15ece9434\"}, \"host\": \"events.retarus.com\", \"ts\": \"2018-10-16 15:03:43 +0200\", \"version\": \"1.0\", \"sourceIp\": \"xxx.xxx.xxx.xxx\", \"sender\": \"xxxxxxx@retarus.com\", \"type\": \"Sandboxing\", \"direction\": \"INBOUND\", \"recipient\": \"xxxxxxx@retarus.de\", \"mimeId\": \"<37357C96.xxxxxxx@retarus.net>\", \"status\": \"SUSPICIOUS\", \"class\": \"THREAT\", \"rmxId\": \"20181016-145902-xxxxxx-0@mailin08\"}",
        "event": {
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ]
        },
        "observer": {
            "version": "1.0",
            "hostname": "events.retarus.com"
        },
        "organization": {
            "id": "CuNo"
        },
        "source": {
            "ip": "xxx.xxx.xxx.xxx",
            "domain": "retarus.com",
            "address": "retarus.com",
            "top_level_domain": "com",
            "registered_domain": "retarus.com"
        },
        "destination": {
            "domain": "retarus.de",
            "address": "retarus.de",
            "top_level_domain": "de",
            "registered_domain": "retarus.de"
        },
        "retarus": {
            "timestamp": "2018-10-16 15:03:43 +0200",
            "email_direction": "INBOUND",
            "mime_message_id": "<37357C96.xxxxxxx@retarus.net>",
            "message_id": "20181016-145902-xxxxxx-0@mailin08",
            "recipient": "xxxxxxx@retarus.de",
            "sender": "xxxxxxx@retarus.com",
            "status": "SUSPICIOUS",
            "class": "THREAT",
            "type": "Sandboxing"
        },
        "action": {
            "name": "THREAT",
            "outcome": "failure"
        },
        "file": {
            "hash": {
                "sha256": "sha256"
            }
        },
        "related": {
            "hash": [
                "sha256"
            ],
            "hosts": [
                "events.retarus.com",
                "retarus.com",
                "retarus.de"
            ],
            "ip": [
                "xxx.xxx.xxx.xxx"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`destination.domain` | `keyword` | The domain name of the destination. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.hash.md5` | `keyword` | MD5 hash. |
|`file.hash.sha1` | `keyword` | SHA1 hash. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.hash.sha512` | `keyword` | SHA512 hash. |
|`file.hash.ssdeep` | `keyword` | SSDEEP hash. |
|`file.mimeType` | `keyword` | MIME type of the detected file (only included if threat type is VIRUS) |
|`observer.hostname` | `keyword` | Hostname of the observer. |
|`observer.version` | `keyword` | Observer version. |
|`organization.id` | `keyword` | Unique identifier for the organization. |
|`retarus.class` | `keyword` | Classification of the event |
|`retarus.email_direction` | `keyword` | Possible values are: INBOUND | OUTBOUND |
|`retarus.message_id` | `keyword` | Retarus unique message ID |
|`retarus.mime_message_id` | `keyword` | Mime message ID |
|`retarus.phishing_identifier` | `long` | Phishing identifier (if threat type is “URL”) |
|`retarus.recipient` | `keyword` | Recipient of the message (envTo) |
|`retarus.sender` | `keyword` | Sender of the message (envFrom) |
|`retarus.status` | `keyword` | Possible values are: - for threat events: INFECTED | DETECTED | SUSPICIOUS, - for MTA events: ACCEPTED |
|`retarus.timestamp` | `keyword` | Timestamp of the message in YYYY-MM-DD hh:mm:ss +hhmm |
|`retarus.type` | `keyword` | Feature which the event is for possible values are: MultiScan, CxO, Sandboxing, PZD, MTA |
|`retarus.virus_name` | `keyword` | Virus name(s) found |
|`source.domain` | `keyword` | The domain name of the source. |
|`source.ip` | `ip` | IP address of the source. |
|`url.full` | `wildcard` | Full unparsed URL. |

