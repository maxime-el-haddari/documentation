
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | PAM authentication mechanism |
| `Process command-line parameters` | Common Linux processes (cron, ssh, sudo) |
| `Process use of network` | SSH and PAM daemon |








## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "auth_conversation_failed.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-07-02T13:45:50.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sudo\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"err\",\"EventTime\" : \"2019-07-02T13:45:50+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"pam_unix(sudo:auth): conversation failed\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-07-02T13:45:50Z\"},\"category\" : \"authpriv\",\"level\" : \"err\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "error",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-07-02T13:45:50.0000000Z",
        "azure_linux": {
            "message": "pam_unix(sudo:auth): conversation failed"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "action": {
            "name": "sudo:auth",
            "type": "open",
            "outcome": "failure"
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "auth_no_identity.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-07-02T13:46:32.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sudo\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"crit\",\"EventTime\" : \"2019-07-02T13:46:32+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"pam_unix(sudo:auth): auth could not identify password for [omsagent]\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-07-02T13:46:32Z\"},\"category\" : \"authpriv\",\"level\" : \"crit\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "critical",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-07-02T13:46:32.0000000Z",
        "azure_linux": {
            "message": "pam_unix(sudo:auth): auth could not identify password for [omsagent]"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "action": {
            "name": "sudo:auth",
            "type": "open",
            "outcome": "failure"
        },
        "user": {
            "name": "omsagent"
        },
        "related": {
            "user": [
                "omsagent"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "cron_command1.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-06-27T14:50:01.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"CROND\",\"pid\" : \"21188\",\"Ignore\" : \"syslog\",\"Facility\" : \"cron\",\"Severity\" : \"info\",\"EventTime\" : \"2019-06-27T14:50:01+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"(root) CMD (/usr/lib64/sa/sa1 1 1)\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-06-27T14:50:01Z\"},\"category\" : \"cron\",\"level\" : \"info\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-06-27T14:50:01.0000000Z",
        "azure_linux": {
            "message": "(root) CMD (/usr/lib64/sa/sa1 1 1)"
        },
        "process": {
            "parent": {
                "pid": 21188
            },
            "command_line": "/usr/lib64/sa/sa1 1 1",
            "executable": "/usr/lib64/sa/sa1"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "user": {
            "name": "root"
        },
        "related": {
            "user": [
                "root"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "cron_command2.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-06-27T14:29:01.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"CROND\",\"pid\" : \"16373\",\"Ignore\" : \"syslog\",\"Facility\" : \"cron\",\"Severity\" : \"info\",\"EventTime\" : \"2019-06-27T14:29:01+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"(root) CMD ([ -f /etc/krb5.keytab ] && [ \\\\( ! -f /etc/opt/omi/creds/omi.keytab \\\\) -o \\\\( /etc/krb5.keytab -nt /etc/opt/omi/creds/omi.keytab \\\\) ] && /opt/omi/bin/support/ktstrip /etc/krb5.keytab /etc/opt/omi/creds/omi.keytab >/dev/null 2>&1 || true)\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-06-27T14:29:01Z\"},\"category\" : \"cron\",\"level\" : \"info\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-06-27T14:29:01.0000000Z",
        "azure_linux": {
            "message": "(root) CMD ([ -f /etc/krb5.keytab ] && [ \\( ! -f /etc/opt/omi/creds/omi.keytab \\) -o \\( /etc/krb5.keytab -nt /etc/opt/omi/creds/omi.keytab \\) ] && /opt/omi/bin/support/ktstrip /etc/krb5.keytab /etc/opt/omi/creds/omi.keytab >/dev/null 2>&1 || true)"
        },
        "process": {
            "parent": {
                "pid": 16373
            },
            "command_line": "[ -f /etc/krb5.keytab ] && [ \\( ! -f /etc/opt/omi/creds/omi.keytab \\) -o \\( /etc/krb5.keytab -nt /etc/opt/omi/creds/omi.keytab \\) ] && /opt/omi/bin/support/ktstrip /etc/krb5.keytab /etc/opt/omi/creds/omi.keytab >/dev/null 2>&1 || true"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "user": {
            "name": "root"
        },
        "related": {
            "user": [
                "root"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "disconnected.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-06-27T14:50:51.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sshd\",\"pid\" : \"14020\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"info\",\"EventTime\" : \"2019-06-27T14:50:51+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"Received disconnect from 185.122.161.248 port 39070:11: disconnected by user\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-06-27T14:50:51Z\"},\"category\" : \"authpriv\",\"level\" : \"info\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-06-27T14:50:51.0000000Z",
        "azure_linux": {
            "message": "Received disconnect from 185.122.161.248 port 39070:11: disconnected by user"
        },
        "process": {
            "pid": 14020
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "source": {
            "ip": "185.122.161.248",
            "port": 39070,
            "address": "185.122.161.248"
        },
        "related": {
            "ip": [
                "185.122.161.248"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "omsagent_command.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-06-27T14:48:18.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sudo\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"notice\",\"EventTime\" : \"2019-06-27T14:48:18+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"omsagent : TTY=unknown ; PWD=/opt/microsoft/omsconfig/Scripts/2.6x-2.7x ; USER=root ; COMMAND=/opt/microsoft/omsconfig/Scripts/OMSYumUpdates.sh\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-06-27T14:48:18Z\"},\"category\" : \"authpriv\",\"level\" : \"notice\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-06-27T14:48:18.0000000Z",
        "azure_linux": {
            "message": "omsagent : TTY=unknown ; PWD=/opt/microsoft/omsconfig/Scripts/2.6x-2.7x ; USER=root ; COMMAND=/opt/microsoft/omsconfig/Scripts/OMSYumUpdates.sh"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "user": {
            "name": "root"
        },
        "process": {
            "command_line": "/opt/microsoft/omsconfig/Scripts/OMSYumUpdates.sh",
            "executable": "/opt/microsoft/omsconfig/Scripts/OMSYumUpdates.sh",
            "working_directory": "/opt/microsoft/omsconfig/Scripts/2.6x-2.7x"
        },
        "action": {
            "outcome": "success"
        },
        "related": {
            "user": [
                "root"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "omsagent_command2.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-07-02T13:46:15.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sudo\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"notice\",\"EventTime\" : \"2019-07-02T13:46:15+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"omsagent : TTY=unknown ; PWD=/ ; USER=root ; COMMAND=/bin/test -r /var/lib/docker/containers/bf64bddcdb7d18a3090980d2539e2c15c924138f489c280871941064850f7d16/bf64bddcdb7d18a3090980d2539e2c15c924138f489c280871941064850f7d16-json.log\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-07-02T13:46:15Z\"},\"category\" : \"authpriv\",\"level\" : \"notice\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-07-02T13:46:15.0000000Z",
        "azure_linux": {
            "message": "omsagent : TTY=unknown ; PWD=/ ; USER=root ; COMMAND=/bin/test -r /var/lib/docker/containers/bf64bddcdb7d18a3090980d2539e2c15c924138f489c280871941064850f7d16/bf64bddcdb7d18a3090980d2539e2c15c924138f489c280871941064850f7d16-json.log"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "user": {
            "name": "root"
        },
        "process": {
            "command_line": "/bin/test -r /var/lib/docker/containers/bf64bddcdb7d18a3090980d2539e2c15c924138f489c280871941064850f7d16/bf64bddcdb7d18a3090980d2539e2c15c924138f489c280871941064850f7d16-json.log",
            "executable": "/bin/test",
            "working_directory": "/"
        },
        "action": {
            "outcome": "success"
        },
        "related": {
            "user": [
                "root"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "session_closed.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-06-27T14:48:28.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sudo\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"info\",\"EventTime\" : \"2019-06-27T14:48:28+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"pam_unix(sudo:session): session closed for user root\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-06-27T14:48:28Z\"},\"category\" : \"authpriv\",\"level\" : \"info\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-06-27T14:48:28.0000000Z",
        "azure_linux": {
            "message": "pam_unix(sudo:session): session closed for user root"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "action": {
            "name": "sudo:session",
            "type": "close",
            "outcome": "success"
        },
        "user": {
            "name": "root"
        },
        "related": {
            "user": [
                "root"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "session_opened.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-06-27T14:48:28.0000000Z\",\"resourceId\" : \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"sudo\",\"Ignore\" : \"syslog\",\"Facility\" : \"authpriv\",\"Severity\" : \"info\",\"EventTime\" : \"2019-06-27T14:48:28+0000\",\"SendingHost\" : \"localhost\",\"Msg\" : \"pam_unix(sudo:session): session opened for user root by (uid=0)\",\"hostname\" : \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-06-27T14:48:28Z\"},\"category\" : \"authpriv\",\"level\" : \"info\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-06-27T14:48:28.0000000Z",
        "azure_linux": {
            "message": "pam_unix(sudo:session): session opened for user root by (uid=0)"
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "action": {
            "name": "sudo:session",
            "type": "open",
            "outcome": "success"
        },
        "user": {
            "name": "root"
        },
        "related": {
            "user": [
                "root"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```


=== "systemd_session.json"

    ```json
	
    {
        "message": "{ \"time\" : \"2019-07-02T14:15:01.0000000Z\",\"resourceId\": \"/subscriptions/128ed5ce-4f50-4b5f-a3b0-08233b5a86b6/resourceGroups/demo.sekoia.io/providers/Microsoft.Compute/virtualMachines/LinuxRedhatDesktop\",\"properties\" : {\"ident\" : \"systemd\",\"Ignore\" : \"syslog\",\"Facility\" : \"daemon\",\"Severity\" : \"info\",\"EventTime\" : \"2019-07-02T14:15:01+0000\",\"SendingHost\": \"localhost\",\"Msg\" : \"Started Session 13124 of user omsagent.\",\"hostname\": \"LinuxRedhatDesktop\",\"FluentdIngestTimestamp\" : \"2019-07-02T14:15:01Z\"},\"category\" : \"daemon\",\"level\" : \"info\",\"operationName\" : \"LinuxSyslogEvent\"}",
        "log": {
            "level": "info",
            "hostname": "LinuxRedhatDesktop"
        },
        "@timestamp": "2019-07-02T14:15:01.0000000Z",
        "azure_linux": {
            "message": "Started Session 13124 of user omsagent."
        },
        "os": {
            "family": "linux",
            "platform": "linux"
        },
        "user": {
            "name": "omsagent"
        },
        "action": {
            "type": "open",
            "name": "systemd:session",
            "outcome": "success"
        },
        "related": {
            "user": [
                "omsagent"
            ]
        },
        "host": {
            "name": "LinuxRedhatDesktop"
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`azure_linux.message` | `keyword` | The linux message |
|`log.level` | `keyword` | Log level of the log event. |
|`process.command_line` | `wildcard` | Full command line that started the process. |
|`process.executable` | `keyword` | Absolute path to the process executable. |
|`process.parent.pid` | `long` | Process id. |
|`process.pid` | `long` | Process id. |
|`process.working_directory` | `keyword` | The working directory of the process. |
|`source.domain` | `keyword` | The domain name of the source. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |
|`user.name` | `keyword` | Short name or login of the user. |

