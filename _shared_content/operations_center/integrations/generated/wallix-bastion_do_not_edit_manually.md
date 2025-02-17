
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | WALLIX provides access logs |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `` |
| Type | `end` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "cron.json"

    ```json
	
    {
        "message": "pam_unix(cron:session): session closed for user root",
        "event": {
            "kind": "event",
            "provider": "cron"
        },
        "wallix": {}
    }
    	
	```


=== "pam_unix.json"

    ```json
	
    {
        "message": "pam_unix(sudo:session): session closed for user wabuser",
        "event": {
            "kind": "event",
            "provider": "sudo"
        },
        "wallix": {}
    }
    	
	```


=== "rdpproxy.json"

    ```json
	
    {
        "message": "2022-09-05T10:05:15+02:00 foo-bastion-bar rdpproxy 4597 - - [RDP Session] session_id=\"1830c6973a42698400505688c380\" client_ip=\"1.1.1.1\" target_ip=\"2.2.2.2\" user=\"adm-foobar@corp.net\" device=\"foo-bar-baz\" service=\"RDP\" account=\"adm-foobar@corp.net\" type=\"FOREGROUND_WINDOW_CHANGED\" text=\"Espace de travail - IBM Lotus Notes\" class_name=\"SWT_Window0\" command_line=\"\\\"C:/lotus/Notes852/framework/rcp/eclipse/plugins/com.ibm.rcp.base_6.2.2.20100729-1241\\\\win32\\\\x86\\\\notes2.exe\\\" --launcher.suppressErrors \\\"-nosplash\\\" \\\"-nl\\\" \\\"fr\\\" \\\"-dir\\\" \\\"ltr\\\" \\\"-NPARAMS\\\" \\\"/authenticate\\\" \\\"-RPARAMS\\\" \\\"-name\\\" \\\"IBM Lotus Notes\\\" -personality \\\"com.ibm.rcp.platform.personality\\\" -product \\\"com.ibm.rcp.personality.framework.RCPProduct:com.ibm.notes.branding.notes\\\" -data \\\"c:/Lotus/Notes852/Data/workspace\\\" -configuration \\\"c:/Lotus/Notes852/Data/workspace/.config\\\" -plugincustomization \\\"C:/lotus/Notes852/framework/rcp/plugin_customization.ini\\\" -vm \\\"C:/lotus/Notes852/framework/../jvm/bin/\\\" -startup \\\"C:/lotus/Notes852/framework/rcp/eclipse/plugins/com.ibm.rcp.base_6.2.2.20100729-1241/launcher.jar\\\" -vmargs \\\"-Djava.security.policy=C:/lotus/Notes852/framework/../java.policy\\\" \\\"-Dorg.eclipse.swt.fixCitrix=false\\\" \\\"-Dosgi.framework.extensions=com.ibm.rcp.core.logger.frameworkhook,com.ibm.rds,com.ibm.cds\\\" \\\"-Xscmx64m\\\" \\\"-Xshareclasses:name=xpdplat_.jvm,controlDir=c:/Lotus/Notes852/Data/workspace/.config/org.eclipse.osgi,groupAccess,keep,singleJVM,nonfatal\\\" \\\"-Xgcpolicy:gencon\\\" \\\"-Xjit:noResumableTrapHandler\\\" \\\"-Xmaxt0.6\\\" \\\"-Xmca8k\\\" \\\"-Xminf0.1\\\" \\\"-Xmn7m\\\" \\\"-Xms48m\\\" \\\"-Xmx256m\\\" \\\"-Xnolinenumbers\\\" \\\"-Xverify:none\\\" \\\"-Xquickstart\\\" \\\"-Xscmaxaot12m\\\" \\\"-Xtrace:none\\\" \\\"-Xzero\\\" -Drcp.home=\\\"C:\\\\lotus\\\\Notes852\\\\framework\\\" -Drcp.data=\\\"c:/Lotus/Notes852/Data/workspace\\\" -Dosgi.splashPath=\\\"platform:/base/../../shared/eclipse/plugins/com.ibm.notes.branding,platform:/base/../../shared/eclipse/plugins/com.ibm.notes.branding.nl1,platform:/base/../.shared/eclipse/plugins/com.ibm.notes.branding.nl2,platform:/base/../../shared/eclipse/plugins/com.ibm.notes.branding.nl3\\\" -Dcom.ibm.rcp.install.id=\\\"1320657906134\\\" -Drcp.install.config=\\\"user\\\" -Declipse.registry.nulltoken=\\\"true\\\" -Dautopd.logfile.generations=\\\"3\\\" -Dorg.apache.xerces.xni.parser.XMLParserConfiguration=\\\"org.apache.xerces.parsers.XIncludeAwareParserConfiguration\\\" -Dcom.ibm.pvc.webcontainer.http.address=\\\"localhost\\\" -Dosgi.nl.user=\\\"true\\\" -Dautopd.instance.area=\\\"c:/Lotus/Notes852/Data/workspace/autopd\\\" -Dorg.eclipse.swt.browser.XULRunnerPath=\\\"C:/lotus/Notes852/framework/rcp/eclipse/plugins/com.ibm.rcp.xulrunner.runtime.win32.x86_6.2.2.20100729-1241/xulrunner\\\" -Djava.util.logging.config.class=\\\"com.ibm.rcp.core.internal.logger.boot.LoggerConfig\\\" -Dcom.ibm.pvc.webcontainer.port=\\\"0,59449\\\" -Dcom.ibm.pvc.webcontainer.vhost.configfile=\\\"C:/lotus/Notes852/framework/shared/eclipse/plugins/com.ibm.collaboration.realtime.webapi_8.0.2.20100802-0849/virtualhost.properties\\\" -Dderby.stream.error.file=\\\"c:/Lotus/Notes852/Data/workspace/logs/derby.log\\\" -Djava.security.properties=\\\"file:C:/lotus/Notes852/framework/rcp/eclipse/plugins/com.ibm.rcp.base_6.2.2.20100729-1241/rcp.security.properties\\\" -Djava.protocol.handler.pkgs=\\\"com.ibm.net.ssl.www.protocol\\\" -Dosgi.hook.configurators.exclude=\\\"org.eclipse.core.runtime.internal.adaptor.EclipseLogHook\\\" -Drcp.osgi.install.area=\\\"C:\\\\lotus\\\\Notes852\\\\framework\\\\rcp\\\\eclipse\\\" -Xbootclasspath/a:\\\"C:/lotus/Notes852/framework/shared/eclipse/plugins/com.ibm.collaboration.realtime.stjavatk_8.0.2.20100802-0849/sslite140-v3.16.jar;C:/lotus/Notes852/framework/rceclipse/plugins/com.ibm.rcp.base_6.2.2.20100729-1241/rcpbootcp.jar\\\"\"\n\n",
        "event": {
            "action": "FOREGROUND_WINDOW_CHANGED",
            "kind": "event"
        },
        "wallix": {
            "type": "FOREGROUND_WINDOW_CHANGED"
        },
        "user": {
            "name": "adm-foobar@corp.net"
        },
        "service": {
            "name": "RDP"
        },
        "destination": {
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ],
            "user": [
                "adm-foobar@corp.net"
            ]
        }
    }
    	
	```


=== "rdpproxy2.json"

    ```json
	
    {
        "message": "2022-09-05T10:05:15+02:00 foo-bastion-bar rdpproxy 13297 - - [RDP Session] session_id=\"1830c403be7caf0c00505688c380\" client_ip=\"1.1.1.1\" target_ip=\"2.2.2.2\" user=\"adm-bar\" device=\"foo-bastion-bar\" service=\"RDP\" account=\"adm-bar@corp.net\" type=\"FOREGROUND_WINDOW_CHANGED\" text=\"Remote Desktop Manager Free [FOO-BAR-P01]\" class_name=\"WindowsForms10.Window.8.app.0.13965fa_r6_ad1\" command_line=\"\\\"C:\\\\Program Files (x86)\\\\Devolutions\\\\Remote Desktop Manager Free\\\\RemoteDesktopManagerFree.exe\\\" \"\n\n",
        "event": {
            "action": "FOREGROUND_WINDOW_CHANGED",
            "kind": "event"
        },
        "wallix": {
            "type": "FOREGROUND_WINDOW_CHANGED"
        },
        "user": {
            "name": "adm-bar"
        },
        "service": {
            "name": "RDP"
        },
        "destination": {
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ],
            "user": [
                "adm-bar"
            ]
        }
    }
    	
	```


=== "rexec.json"

    ```json
	
    {
        "message": "rexec line 15: Deprecated option UsePrivilegeSeparation",
        "event": {
            "kind": "event",
            "provider": "sshd"
        },
        "wallix": {}
    }
    	
	```


=== "sshprox.json"

    ```json
	
    {
        "message": "[sshproxy] psid=\"161607370130601\" type=\"INCOMING_CONNECTION\" src_ip=\"10.17.86.250\" src_port=\"53344\"",
        "event": {
            "action": "INCOMING_CONNECTION",
            "kind": "event",
            "provider": "sshproxy"
        },
        "wallix": {
            "type": "INCOMING_CONNECTION"
        },
        "source": {
            "ip": "10.17.86.250",
            "port": 53344,
            "address": "10.17.86.250"
        },
        "related": {
            "ip": [
                "10.17.86.250"
            ]
        }
    }
    	
	```


=== "sshproxy.json"

    ```json
	
    {
        "message": "sshproxy: [SSH Session] session_id=\"168bd3b417f437ae005056b60af6\" client_ip=\"10.10.43.84\" target_ip=\"10.10.47.53\" user=\"user01\" device=\"10.10.47.53\" service=\"ssh\" account=\"root\" type=\"SESSION_DISCONNECTION\" duration=\"0:00:05\"",
        "event": {
            "action": "SESSION_DISCONNECTION",
            "kind": "event"
        },
        "wallix": {
            "type": "SESSION_DISCONNECTION"
        },
        "user": {
            "name": "user01"
        },
        "service": {
            "name": "ssh"
        },
        "source": {
            "ip": "10.10.43.84",
            "address": "10.10.43.84"
        },
        "host": {
            "ip": [
                "10.10.47.53"
            ]
        },
        "destination": {
            "ip": "10.10.47.53",
            "address": "10.10.47.53"
        },
        "related": {
            "ip": [
                "10.10.43.84",
                "10.10.47.53"
            ],
            "user": [
                "user01"
            ]
        }
    }
    	
	```


=== "sshsession.json"

    ```json
	
    {
        "message": "[SSH Session] session_id=\"182f9642c81320eb0050568e16d9\" client_ip=\"1.1.1.1\" target_ip=\"1.1.1.1\" user=\"username123@corp.net\" device=\"1.1.1.1\" service=\"SSH\" account=\"username123\" type=\"SESSION_DISCONNECTION\" duration=\"0:59:57\"",
        "event": {
            "action": "SESSION_DISCONNECTION",
            "kind": "event",
            "provider": "SSH Session"
        },
        "wallix": {
            "type": "SESSION_DISCONNECTION"
        },
        "user": {
            "name": "username123@corp.net"
        },
        "service": {
            "name": "SSH"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "host": {
            "ip": [
                "1.1.1.1"
            ]
        },
        "destination": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ],
            "user": [
                "username123@corp.net"
            ]
        }
    }
    	
	```


=== "sshsession2.json"

    ```json
	
    {
        "message": "[SSH Session] session_id=\"1830cbf7a55a11dd005056b01296\" client_ip=\"1.1.1.1\" target_ip=\"ip-foo-bar-baz.corp.net\" user=\"user.name@corp.net\" device=\"DEVICE-FOO\" service=\"SSH\" account=\"username\" type=\"SESSION_ESTABLISHED_SUCCESSFULLY\"",
        "event": {
            "action": "SESSION_ESTABLISHED_SUCCESSFULLY",
            "kind": "event",
            "provider": "SSH Session"
        },
        "wallix": {
            "type": "SESSION_ESTABLISHED_SUCCESSFULLY"
        },
        "user": {
            "name": "user.name@corp.net"
        },
        "service": {
            "name": "SSH"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ],
            "user": [
                "user.name@corp.net"
            ]
        }
    }
    	
	```


=== "sudo.json"

    ```json
	
    {
        "message": "root : TTY=unknown ; PWD=/root ; USER=wabuser ; COMMAND=/opt/wab/bin/WABCleanApprovals close",
        "event": {
            "kind": "event",
            "provider": "sudo"
        },
        "wallix": {},
        "user": {
            "name": "wabuser ;"
        },
        "process": {
            "command_line": "/opt/wab/bin/WABCleanApprovals close"
        },
        "related": {
            "user": [
                "wabuser ;"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_ConnectionPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"ConnectionPolicy\" object=\"QA_CONNECTION_POLICY_SSH_AGENT_FORWARDING\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"cn [QA_CONNECTION_POLICY_SSH_AGENT_FORWARDING], protocol [SSH], services [], methods [PASSWORD_VAULT, PUBKEY_VAULT, PUBKEY_AGENT_FORWARDING and 1 other(s)], Data [server_pubkey[server_pubkey_check]: '1', server_pubkey[server_pubkey_create_message]: '1', server_pubkey[server_access_allowed_message]: '0', server_pubkey[server_pubkey_success_message]: '0', server_pubkey[server_pubkey_failure_message]: '1', server_pubkey[server_pubkey_store]: 'True', trace[log_all_kbd]: 'False', startup_scenario[ask_startup]: 'False', startup_scenario[show_output]: 'True', startup_scenario[enable]: 'False', startup_scenario[timeout]: '10', startup_scenario[scenario]: '', general[transformation_rule]: '', session[inactivity_timeout]: '0', session[allow_multi_channels]: 'False', algorithms[kex_algos]: '', algorithms[compression_algos]: '', algorithms[cipher_algos]: '', algorithms[integrity_algos]: '']\"",
        "event": {
            "action": "ConnectionPolicy",
            "reason": "cn [QA_CONNECTION_POLICY_SSH_AGENT_FORWARDING], protocol [SSH], services [], methods [PASSWORD_VAULT, PUBKEY_VAULT, PUBKEY_AGENT_FORWARDING and 1 other(s)], Data [server_pubkey[server_pubkey_check]: '1', server_pubkey[server_pubkey_create_message]: '1', server_pubkey[server_access_allowed_message]: '0', server_pubkey[server_pubkey_success_message]: '0', server_pubkey[server_pubkey_failure_message]: '1', server_pubkey[server_pubkey_store]: 'True', trace[log_all_kbd]: 'False', startup_scenario[ask_startup]: 'False', startup_scenario[show_output]: 'True', startup_scenario[enable]: 'False', startup_scenario[timeout]: '10', startup_scenario[scenario]: '', general[transformation_rule]: '', session[inactivity_timeout]: '0', session[allow_multi_channels]: 'False', algorithms[kex_algos]: '', algorithms[compression_algos]: '', algorithms[cipher_algos]: '', algorithms[integrity_algos]: '']",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_CONNECTION_POLICY_SSH_AGENT_FORWARDING",
            "type": "ConnectionPolicy",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_CredChgInfo.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"CredChgInfo\" object=\"local1/None\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"service_name ['None' to 'XE'], host ['None' to 'my.db.hostname'], port ['None' to '1234']\"",
        "event": {
            "action": "CredChgInfo",
            "reason": "service_name ['None' to 'XE'], host ['None' to 'my.db.hostname'], port ['None' to '1234']",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "local1/None",
            "type": "CredChgInfo",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_CredChgPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"CredChgPolicy\" object=\"QA_PASSWORD_CHANGE_POLICY\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"pwdLength [8], specialChars [1], changePeriod []\"",
        "event": {
            "action": "CredChgPolicy",
            "reason": "pwdLength [8], specialChars [1], changePeriod []",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_PASSWORD_CHANGE_POLICY",
            "type": "CredChgPolicy",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Globaldomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Globaldomain\" object=\"QA_DOMAIN_SIMPLE\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"cn [QA_DOMAIN_SIMPLE], name [QA_DOMAIN_SIMPLE]\"",
        "event": {
            "action": "Globaldomain",
            "reason": "cn [QA_DOMAIN_SIMPLE], name [QA_DOMAIN_SIMPLE]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_DOMAIN_SIMPLE",
            "type": "Globaldomain",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_LdapMapping.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"LdapMapping\" object=\"<QA_DOMAIN_1, OU=Group> in user_group_154954913825 GROUP\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"ldapGroup [OU=Group], domain [QA_DOMAIN_1], group [user_group_154954913825]\"",
        "event": {
            "action": "LdapMapping",
            "reason": "ldapGroup [OU=Group], domain [QA_DOMAIN_1], group [user_group_154954913825]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<QA_DOMAIN_1, OU=Group> in user_group_154954913825 GROUP",
            "type": "LdapMapping",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Ldapdomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Ldapdomain\" object=\"QA_DOMAIN_1\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"description [], ldapDomain [domain1.qa], defaultLanguage [en], defaultEmailDomain [wallix], groupAttribute [memberOf], snAttribute [displayName], emailAttribute [mail], languageAttribute [preferredLanguage], isDefaultDomain [True]\"",
        "event": {
            "action": "Ldapdomain",
            "reason": "description [], ldapDomain [domain1.qa], defaultLanguage [en], defaultEmailDomain [wallix], groupAttribute [memberOf], snAttribute [displayName], emailAttribute [mail], languageAttribute [preferredLanguage], isDefaultDomain [True]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_DOMAIN_1",
            "type": "Ldapdomain",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Localdomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Localdomain\" object=\"local\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"cn [local], device [QA_DEVICE_SSH_SHELL_SESSION]\"",
        "event": {
            "action": "Localdomain",
            "reason": "cn [local], device [QA_DEVICE_SSH_SHELL_SESSION]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "local",
            "type": "Localdomain",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Notification.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Notification\" object=\"notification_154955208543\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"dest [qa-notify@wallix.com], flag [0], isNotificationEnable [True], type [EMAIL]\"",
        "event": {
            "action": "Notification",
            "reason": "dest [qa-notify@wallix.com], flag [0], isNotificationEnable [True], type [EMAIL]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "notification_154955208543",
            "type": "Notification",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Period.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Period\" object=\"<2030-01-01 to 2099-12-31 , 00:00:00 to 23:59:00, 127>\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"startDate [2030-01-01], endDate [2099-12-31], startTime [00:00:00], endTime [23:59:00], weekmask [127]\"",
        "event": {
            "action": "Period",
            "reason": "startDate [2030-01-01], endDate [2099-12-31], startTime [00:00:00], endTime [23:59:00], weekmask [127]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<2030-01-01 to 2099-12-31 , 00:00:00 to 23:59:00, 127>",
            "type": "Period",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Profil.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Profile\" object=\"QA_PROFILE_IP_FORBIDDEN\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"ip_limitation [1.1.1.1], habilitationFlag [1], groups_limitation [], groups_member []\"",
        "event": {
            "action": "Profile",
            "reason": "ip_limitation [1.1.1.1], habilitationFlag [1], groups_limitation [], groups_member []",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_PROFILE_IP_FORBIDDEN",
            "type": "Profile",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Restriction.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Restriction\" object=\"<kill, Kill.+Softly, SSH_SHELL_SESSION> in GROUP QA_USER_GROUP_UNIX_KILL\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"action [kill], data [Kill.+Softly], groups [QA_USER_GROUP_UNIX_KILL], subprotocol [SSH_SHELL_SESSION]\"",
        "event": {
            "action": "Restriction",
            "reason": "action [kill], data [Kill.+Softly], groups [QA_USER_GROUP_UNIX_KILL], subprotocol [SSH_SHELL_SESSION]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<kill, Kill.+Softly, SSH_SHELL_SESSION> in GROUP QA_USER_GROUP_UNIX_KILL",
            "type": "Restriction",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Service.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Service\" object=\"QA_DEVICE_SSH_SHELL_SESSION:SSH\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"protocol [SSH], port [22], subprotocols [SSH_SHELL_SESSION], connectionPolicy [SSH]\"",
        "event": {
            "action": "Service",
            "reason": "protocol [SSH], port [22], subprotocols [SSH_SHELL_SESSION], connectionPolicy [SSH]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_DEVICE_SSH_SHELL_SESSION:SSH",
            "type": "Service",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Targetgroup.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Targetgroup\" object=\"QA_DEVICE_GROUP_UNIX\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"Users [], Targets [__WIL__@am_il_domain@QA_DEVICE_TELNET:TELNET, __WAM__@am_il_domain@QA_DEVICE_SSH_SCP_DOWN:SSH, pubkey_account_without_password@local@QA_DEVICE_SSH_FORWARDING:SSH and 35 other(s)], Profiles_limit [], Timeframes [allthetime]\"",
        "event": {
            "action": "Targetgroup",
            "reason": "Users [], Targets [__WIL__@am_il_domain@QA_DEVICE_TELNET:TELNET, __WAM__@am_il_domain@QA_DEVICE_SSH_SCP_DOWN:SSH, pubkey_account_without_password@local@QA_DEVICE_SSH_FORWARDING:SSH and 35 other(s)], Profiles_limit [], Timeframes [allthetime]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_DEVICE_GROUP_UNIX",
            "type": "Targetgroup",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_TimeFrame.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"TimeFrame\" object=\"timeframe_154954856399\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"description [], isOvertimable [False]\"",
        "event": {
            "action": "TimeFrame",
            "reason": "description [], isOvertimable [False]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "timeframe_154954856399",
            "type": "TimeFrame",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_User.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"User\" object=\"QA_USER_IP_FORBIDDEN\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"email [qa-notify@wallix.com], preferredLanguage [en], host [1.1.1.1], profile [user], groups [QA_USER_GROUP_UNIX], forceChangePwd [False], userPassword [********], userauths [local]\"",
        "event": {
            "action": "User",
            "reason": "email [qa-notify@wallix.com], preferredLanguage [en], host [1.1.1.1], profile [user], groups [QA_USER_GROUP_UNIX], forceChangePwd [False], userPassword [********], userauths [local]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_USER_IP_FORBIDDEN",
            "type": "User",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_UserAuth.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"UserAuth\" object=\"QA_USER_AUTH_KERBEROS\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"wabAuthType [KERBEROS], description [], port [88], host [10.10.45.148], kerDomControler [QA.IFR.LAN]\"",
        "event": {
            "action": "UserAuth",
            "reason": "wabAuthType [KERBEROS], description [], port [88], host [10.10.45.148], kerDomControler [QA.IFR.LAN]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_USER_AUTH_KERBEROS",
            "type": "UserAuth",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_Usergroup.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Usergroup\" object=\"QA_USER_GROUP_UNIX\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"Users [], Profiles_limit [], Timeframes [allthetime]\"",
        "event": {
            "action": "Usergroup",
            "reason": "Users [], Profiles_limit [], Timeframes [allthetime]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_USER_GROUP_UNIX",
            "type": "Usergroup",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_X509Parameters.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"X509 Parameters\" user=\"admin\" client_ip=\"192.168.0.12\" infos=\"CRL [url fetched hourly]\"",
        "event": {
            "action": "X509 Parameters",
            "reason": "CRL [url fetched hourly]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "X509 Parameters",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.0.12",
            "address": "192.168.0.12"
        },
        "related": {
            "ip": [
                "192.168.0.12"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_account.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Account\" object=\"account_with_approval@QA_DOMAIN_SIMPLE\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"name [account_with_approval], login [account_with_approval], autoChangePassword [True], autoChangeSSHKey [True], isExternalVault [False]\"",
        "event": {
            "action": "Account",
            "reason": "name [account_with_approval], login [account_with_approval], autoChangePassword [True], autoChangeSSHKey [True], isExternalVault [False]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "account_with_approval@QA_DOMAIN_SIMPLE",
            "type": "Account",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_answer.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"list\" type=\"accountactivity\" object=\"168c1c48f141e911005056b60af6\" user=\"admin\" client_ip=\"10.10.43.84\" infos=",
        "event": {
            "action": "accountactivity",
            "kind": "event",
            "type": [
                "access"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "168c1c48f141e911005056b60af6",
            "type": "accountactivity",
            "action": "list"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.43.84",
            "address": "10.10.43.84"
        },
        "related": {
            "ip": [
                "10.10.43.84"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_apikey.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Apikey\" object=\"apikey_154954880399\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"cn [apikey_154954880399], apikey [********], ipLimitation []\"",
        "event": {
            "action": "Apikey",
            "reason": "cn [apikey_154954880399], apikey [********], ipLimitation []",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "apikey_154954880399",
            "type": "Apikey",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_application.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Application\" object=\"QA_APP_DUMMY\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"target [account@local@QA_DEVICE_DUMMY_WIN:RDP]\"",
        "event": {
            "action": "Application",
            "reason": "target [account@local@QA_DEVICE_DUMMY_WIN:RDP]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_APP_DUMMY",
            "type": "Application",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_apppath.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Apppath\" object=\"account@local@QA_DEVICE_DUMMY_WIN:RDP[<C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe>:<C:\\>]\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"program [C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe], workingdir [C:\\]\"",
        "event": {
            "action": "Apppath",
            "reason": "program [C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe], workingdir [C:\\]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "account@local@QA_DEVICE_DUMMY_WIN:RDP[<C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe>:<C:\\>]",
            "type": "Apppath",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_approval.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Approval\" object=\"<Approval(uid=\\'168c849f0378d7f4005056b69255\\', status=3, begin=2019-02-07 15:08:00, end=2019-02-07 15:18:00, quorum=1)>\\n\" user=\"user_154954851465\" client_ip=\"10.10.45.212\" infos=\"status [3], begin [2019-02-07 15:08:00], creation [2019-02-07 15:08:35.382824], duration [600], end [2019-02-07 15:18:00], username [user_154954851465], targetname [user_1@local@QA_DEVICE_WITH_APPROVAL_OPTIONAL_COMMENT_AND_TICKET:SSH], quorum [1], email [qa-notify@wallix.com], language [en]\"",
        "event": {
            "action": "Approval",
            "reason": "status [3], begin [2019-02-07 15:08:00], creation [2019-02-07 15:08:35.382824], duration [600], end [2019-02-07 15:18:00], username [user_154954851465], targetname [user_1@local@QA_DEVICE_WITH_APPROVAL_OPTIONAL_COMMENT_AND_TICKET:SSH], quorum [1], email [qa-notify@wallix.com], language [en]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<Approval(uid=\\'168c849f0378d7f4005056b69255\\', status=3, begin=2019-02-07 15:08:00, end=2019-02-07 15:18:00, quorum=1)>\\n",
            "type": "Approval",
            "action": "add"
        },
        "user": {
            "name": "user_154954851465"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "user_154954851465"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_authorization.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Authorization\" object=\"QA_USER_GROUP_UNIX:QA_DEVICE_GROUP_UNIX\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"cn [unix_group], targetGroupIdentifier [QA_DEVICE_GROUP_UNIX], isRecorded [True], isCritical [False], userAccess [False], proxyAccess [True], subprotocols [SSH_SHELL_SESSION, SSH_REMOTE_COMMAND, SSH_SCP_UP and 7 other(s)], approvalRequired [False], hasComment [False], mandatoryComment [False], hasTicket [False], mandatoryTicket [False], activeQuorum [0], inactiveQuorum [0]\"",
        "event": {
            "action": "Authorization",
            "reason": "cn [unix_group], targetGroupIdentifier [QA_DEVICE_GROUP_UNIX], isRecorded [True], isCritical [False], userAccess [False], proxyAccess [True], subprotocols [SSH_SHELL_SESSION, SSH_REMOTE_COMMAND, SSH_SCP_UP and 7 other(s)], approvalRequired [False], hasComment [False], mandatoryComment [False], hasTicket [False], mandatoryTicket [False], activeQuorum [0], inactiveQuorum [0]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_USER_GROUP_UNIX:QA_DEVICE_GROUP_UNIX",
            "type": "Authorization",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_checkoutpolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"CheckoutPolicy\" object=\"QA_CHECKOUT_POLICY_LOCK\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"enableLock [True], duration [600], extension [0], maxDuration [600], checkinChange [0]\"",
        "event": {
            "action": "CheckoutPolicy",
            "reason": "enableLock [True], duration [600], extension [0], maxDuration [600], checkinChange [0]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_CHECKOUT_POLICY_LOCK",
            "type": "CheckoutPolicy",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_cluster.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Cluster\" object=\"cluster_154954837225\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"member_targets [account_154954837122@local1@device_154954837021:rdp, account_154954837224@local1@device_154954837123:rdp]\"",
        "event": {
            "action": "Cluster",
            "reason": "member_targets [account_154954837122@local1@device_154954837021:rdp, account_154954837224@local1@device_154954837123:rdp]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "cluster_154954837225",
            "type": "Cluster",
            "action": "add"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_add_type_device.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Device\" object=\"QA_DEVICE_SSH_SHELL_SESSION\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"Host [10.10.45.148], Alias [QA_DEVICE_SSH_SHELL_SESSION_ALIAS]\"",
        "event": {
            "action": "Device",
            "reason": "Host [10.10.45.148], Alias [QA_DEVICE_SSH_SHELL_SESSION_ALIAS]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_DEVICE_SSH_SHELL_SESSION",
            "type": "Device",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_backup_type_backup_restore.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"backup\" type=\"Backup/Restore\" user=\"admin\" client_ip=\"192.168.0.12\" infos=\"Backup ['wab-6.0-cspn_2019-02-04_16-59-11.wbk' saved]\"",
        "event": {
            "action": "Backup/Restore",
            "reason": "Backup ['wab-6.0-cspn_2019-02-04_16-59-11.wbk' saved]",
            "kind": "event",
            "category": "database",
            "provider": "wabengine"
        },
        "wallix": {
            "type": "Backup/Restore",
            "action": "backup"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.0.12",
            "address": "192.168.0.12"
        },
        "related": {
            "ip": [
                "192.168.0.12"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_ConnectionPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"ConnectionPolicy\" object=\"connection_policy_154954884812\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "ConnectionPolicy",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "connection_policy_154954884812",
            "type": "ConnectionPolicy",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_CredChgInfo.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"CredChgInfo\" object=\"<CredChgInfo(uid=\\'168c849848928a52005056b69255\\')>\\n\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "CredChgInfo",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<CredChgInfo(uid=\\'168c849848928a52005056b69255\\')>\\n",
            "type": "CredChgInfo",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_CredChgPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"CredChgPolicy\" object=\"password_change_policy_name_154954918141\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "CredChgPolicy",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "password_change_policy_name_154954918141",
            "type": "CredChgPolicy",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Globaldomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Globaldomain\" object=\"global_domain_154954904181\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Globaldomain",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "global_domain_154954904181",
            "type": "Globaldomain",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_LdapMapping.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"LdapMapping\" object=\"<QA_DOMAIN_1, OU=Group> in user_group_154954913825 GROUP\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "LdapMapping",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<QA_DOMAIN_1, OU=Group> in user_group_154954913825 GROUP",
            "type": "LdapMapping",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Ldapdomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Ldapdomain\" object=\"domain_154955334782\" user=\"admin\" client_ip=\"192.168.122.1\" infos=\"\"",
        "event": {
            "action": "Ldapdomain",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "domain_154955334782",
            "type": "Ldapdomain",
            "action": "delete"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.122.1",
            "address": "192.168.122.1"
        },
        "related": {
            "ip": [
                "192.168.122.1"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Localdomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Localdomain\" object=\"local1\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Localdomain",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "local1",
            "type": "Localdomain",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Notification.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Notification\" object=\"notification_154955204621\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Notification",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "notification_154955204621",
            "type": "Notification",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Period.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Period\" object=\"<2010-01-01 to 2020-01-01 , 09:30:00 to 18:30:00, 124>\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Period",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<2010-01-01 to 2020-01-01 , 09:30:00 to 18:30:00, 124>",
            "type": "Period",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Profil.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Profile\" object=\"profile_154954924847\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Profile",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "profile_154954924847",
            "type": "Profile",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Service.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Service\" object=\"device_154954928856:ssh\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Service",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "device_154954928856:ssh",
            "type": "Service",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Targetgroup.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Targetgroup\" object=\"target_group_154954938767\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Targetgroup",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "target_group_154954938767",
            "type": "Targetgroup",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_TimeFrame.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"TimeFrame\" object=\"timeframe_154954953374\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "TimeFrame",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "timeframe_154954953374",
            "type": "TimeFrame",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_User.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"User\" object=\"UNKNOWN_USER\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "User",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "UNKNOWN_USER",
            "type": "User",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_UserAuth.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"UserAuth\" object=\"auth_LDAP_154955198487\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "UserAuth",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "auth_LDAP_154955198487",
            "type": "UserAuth",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_Usergroup.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Usergroup\" object=\"user_group_154954962345\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Usergroup",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "user_group_154954962345",
            "type": "Usergroup",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_X509Parameters.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"X509 Parameters\" user=\"admin\" client_ip=\"192.168.0.12\" infos=\"CRL [deleted]\"",
        "event": {
            "action": "X509 Parameters",
            "reason": "CRL [deleted]",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "X509 Parameters",
            "action": "delete"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.0.12",
            "address": "192.168.0.12"
        },
        "related": {
            "ip": [
                "192.168.0.12"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_account.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Account\" object=\"account_154954844398@local1@application_154954844399\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Account",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "account_154954844398@local1@application_154954844399",
            "type": "Account",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_apikey.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Apikey\" object=\"apikey_154954882800\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Apikey",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "apikey_154954882800",
            "type": "Apikey",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_application.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Application\" object=\"application_154954836612\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Application",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "application_154954836612",
            "type": "Application",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_apppath.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Apppath\" object=\"account_154954841440@local1@device_154954841439:rdp[<None>:<C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe>]\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Apppath",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "account_154954841440@local1@device_154954841439:rdp[<None>:<C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe>]",
            "type": "Apppath",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_approval.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Approval\" object=\"<Approval(uid=\\'168c849f0378d7f4005056b69255\\', status=4, begin=2019-02-07 15:08:00, end=2019-02-07 15:18:00, quorum=1)>\\n\" user=\"OPERATOR\" client_ip=\"127.0.0.1\" infos=\"\"",
        "event": {
            "action": "Approval",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<Approval(uid=\\'168c849f0378d7f4005056b69255\\', status=4, begin=2019-02-07 15:08:00, end=2019-02-07 15:18:00, quorum=1)>\\n",
            "type": "Approval",
            "action": "delete"
        },
        "user": {
            "name": "OPERATOR"
        },
        "source": {
            "ip": "127.0.0.1",
            "address": "127.0.0.1"
        },
        "related": {
            "ip": [
                "127.0.0.1"
            ],
            "user": [
                "OPERATOR"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_authorization.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Authorization\" object=\"user_group_154954865272:target_group_154954865373\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Authorization",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "user_group_154954865272:target_group_154954865373",
            "type": "Authorization",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_checkoutpolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"CheckoutPolicy\" object=\"checkout_policy_154954874456\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "CheckoutPolicy",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "checkout_policy_154954874456",
            "type": "CheckoutPolicy",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_cluster.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"delete\" type=\"Cluster\" object=\"cluster_154954875802\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Cluster",
            "kind": "event",
            "type": [
                "deletion"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "cluster_154954875802",
            "type": "Cluster",
            "action": "delete"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_delete_type_device.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"add\" type=\"Device\" object=\"QA_DEVICE_SSH_SHELL_SESSION\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"Host [10.10.45.148], Alias [QA_DEVICE_SSH_SHELL_SESSION_ALIAS]\"",
        "event": {
            "action": "Device",
            "reason": "Host [10.10.45.148], Alias [QA_DEVICE_SSH_SHELL_SESSION_ALIAS]",
            "kind": "event",
            "type": [
                "creation"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "QA_DEVICE_SSH_SHELL_SESSION",
            "type": "Device",
            "action": "add"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_download_type_backup_restore.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"download\" type=\"Backup/Restore\" user=\"admin\" client_ip=\"192.168.0.12\" infos=\"Backup ['wab-6.0-cspn_2019-02-04_16-59-11.wbk' downloaded]\"",
        "event": {
            "action": "Backup/Restore",
            "reason": "Backup ['wab-6.0-cspn_2019-02-04_16-59-11.wbk' downloaded]",
            "kind": "event",
            "category": "database",
            "provider": "wabengine"
        },
        "wallix": {
            "type": "Backup/Restore",
            "action": "download"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.0.12",
            "address": "192.168.0.12"
        },
        "related": {
            "ip": [
                "192.168.0.12"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_ConnectionPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"ConnectionPolicy\" object=\"SSH\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"methods [Add < PASSWORD_VAULT, PUBKEY_VAULT, PASSWORD_INTERACTIVE and 1 other(s) >, Remove < PUBKEY_VAULT, PASSWORD_MAPPING, PASSWORD_VAULT and 1 other(s) >], Data [session[allow_multi_channels]: 'False' => 'on']\"",
        "event": {
            "action": "ConnectionPolicy",
            "reason": "methods [Add < PASSWORD_VAULT, PUBKEY_VAULT, PASSWORD_INTERACTIVE and 1 other(s) >, Remove < PUBKEY_VAULT, PASSWORD_MAPPING, PASSWORD_VAULT and 1 other(s) >], Data [session[allow_multi_channels]: 'False' => 'on']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "SSH",
            "type": "ConnectionPolicy",
            "action": "edit"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_CredChgInfo.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"CredChgInfo\" object=\"local1/None\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "CredChgInfo",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "local1/None",
            "type": "CredChgInfo",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_CredChgPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"CredChgPolicy\" object=\"password_change_policy_name_154954918865\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "CredChgPolicy",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "password_change_policy_name_154954918865",
            "type": "CredChgPolicy",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Globaldomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Globaldomain\" object=\"global_domain_154954904486\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"credchgplugin ['None' to 'Windows'], credchgpolicy ['None' to 'default'], adminAccount ['None' to 'account_154954904487...']\"",
        "event": {
            "action": "Globaldomain",
            "reason": "credchgplugin ['None' to 'Windows'], credchgpolicy ['None' to 'default'], adminAccount ['None' to 'account_154954904487...']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "global_domain_154954904486",
            "type": "Globaldomain",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Ldapdomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Ldapdomain\" object=\"domain_154955334798\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"description ['some description' to 'updated'], snAttribute ['' to 'updated']\"",
        "event": {
            "action": "Ldapdomain",
            "reason": "description ['some description' to 'updated'], snAttribute ['' to 'updated']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "domain_154955334798",
            "type": "Ldapdomain",
            "action": "edit"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Localdomain.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Localdomain\" object=\"local1\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"adminAccount ['None' to 'account_154954837938...']\"",
        "event": {
            "action": "Localdomain",
            "reason": "adminAccount ['None' to 'account_154954837938...']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "local1",
            "type": "Localdomain",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Notification.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Notification\" object=\"notification_154955216694\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"flag ['16' to '0']\"",
        "event": {
            "action": "Notification",
            "reason": "flag ['16' to '0']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "notification_154955216694",
            "type": "Notification",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Profil.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Profile\" object=\"profile_154954927022\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Profile",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "profile_154954927022",
            "type": "Profile",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_PwdPolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"PwdPolicy\" object=\"default\" user=\"admin\" client_ip=\"10.10.45.212\" infos=\"pwdMinLowerLetter ['1' to '0'], rsaMinLength ['4096' to '1024']\"",
        "event": {
            "action": "PwdPolicy",
            "reason": "pwdMinLowerLetter ['1' to '0'], rsaMinLength ['4096' to '1024']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "default",
            "type": "PwdPolicy",
            "action": "edit"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_RecordingOptions.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Recording Options\" user=\"admin\" client_ip=\"10.10.43.28\" infos=\"Recording Options ['No encryption, with checksum' to 'No encryption, no checksum']\"",
        "event": {
            "action": "Recording Options",
            "reason": "Recording Options ['No encryption, with checksum' to 'No encryption, no checksum']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "Recording Options",
            "action": "edit"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.43.28",
            "address": "10.10.43.28"
        },
        "related": {
            "ip": [
                "10.10.43.28"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Service.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Service\" object=\"device_154954931097:ssh\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Service",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "device_154954931097:ssh",
            "type": "Service",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Targetgroup.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Targetgroup\" object=\"target_group_154954945465\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"Description ['some desc' to 'some other desc']\"",
        "event": {
            "action": "Targetgroup",
            "reason": "Description ['some desc' to 'some other desc']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "target_group_154954945465",
            "type": "Targetgroup",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_TimeFrame.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"TimeFrame\" object=\"timeframe_154954954305\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "TimeFrame",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "timeframe_154954954305",
            "type": "TimeFrame",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_User.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"User\" object=\"user_154954924239\" user=\"user_154954924239\" client_ip=\"10.10.45.212\" infos=\"email ['qa-notify@wallix.com...' to 'qa-notify+1@wallix.c...']\"",
        "event": {
            "action": "User",
            "reason": "email ['qa-notify@wallix.com...' to 'qa-notify+1@wallix.c...']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "user_154954924239",
            "type": "User",
            "action": "edit"
        },
        "user": {
            "name": "user_154954924239"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "user_154954924239"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_UserAuth.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"UserAuth\" object=\"auth_LDAP_154955202505\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"description ['None' to 'updated while used b...']\"",
        "event": {
            "action": "UserAuth",
            "reason": "description ['None' to 'updated while used b...']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "auth_LDAP_154955202505",
            "type": "UserAuth",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_Usergroup.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Usergroup\" object=\"user_group_154954965326\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"Description ['some desc' to 'some other desc']\"",
        "event": {
            "action": "Usergroup",
            "reason": "Description ['some desc' to 'some other desc']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "user_group_154954965326",
            "type": "Usergroup",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_X509Parameters.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"X509 Parameters\" user=\"admin\" client_ip=\"192.168.0.12\" infos=\"CRL [file updated]\"",
        "event": {
            "action": "X509 Parameters",
            "reason": "CRL [file updated]",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "X509 Parameters",
            "action": "edit"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.0.12",
            "address": "192.168.0.12"
        },
        "related": {
            "ip": [
                "192.168.0.12"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_action.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Account\" object=\"account_154954837938@local1@application_154954837837\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Account",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "account_154954837938@local1@application_154954837837",
            "type": "Account",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_application.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Application\" object=\"application_154954842057\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Application",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "application_154954842057",
            "type": "Application",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_approval.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Approval\" object=\"<Approval(uid=\\'168c849fa6a347bd005056b69255\\', status=1, begin=2019-02-07 15:08:00, end=2019-02-07 15:18:00, quorum=1)>\\n\" user=\"QA_USER_APPROVER_1\" client_ip=\"10.10.45.212\" infos=\"status ['3' to '1']\"",
        "event": {
            "action": "Approval",
            "reason": "status ['3' to '1']",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "<Approval(uid=\\'168c849fa6a347bd005056b69255\\', status=1, begin=2019-02-07 15:08:00, end=2019-02-07 15:18:00, quorum=1)>\\n",
            "type": "Approval",
            "action": "edit"
        },
        "user": {
            "name": "QA_USER_APPROVER_1"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_USER_APPROVER_1"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_authorization.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Authorization\" object=\"user_group_154954869778:target_group_154954869779\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Authorization",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "user_group_154954869778:target_group_154954869779",
            "type": "Authorization",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_checkoutpolicy.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"CheckoutPolicy\" object=\"checkout_policy_154954875282\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "CheckoutPolicy",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "checkout_policy_154954875282",
            "type": "CheckoutPolicy",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_cluster.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Cluster\" object=\"cluster_154954878267\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Cluster",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "cluster_154954878267",
            "type": "Cluster",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_edit_type_device.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"edit\" type=\"Device\" object=\"device_154954892089\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Device",
            "kind": "event",
            "type": [
                "change"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "device_154954892089",
            "type": "Device",
            "action": "edit"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_list_type_accountactivity.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"list\" type=\"accountactivity\" object=\"168c1c48f141e911005056b60af6\" user=\"admin\" client_ip=\"10.10.43.84\" infos=\"\"",
        "event": {
            "action": "accountactivity",
            "kind": "event",
            "type": [
                "access"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "object": "168c1c48f141e911005056b60af6",
            "type": "accountactivity",
            "action": "list"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "10.10.43.84",
            "address": "10.10.43.84"
        },
        "related": {
            "ip": [
                "10.10.43.84"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_action_list_type_approval.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"list\" type=\"Approval\" user=\"QA_ADMIN\" client_ip=\"10.10.45.212\" infos=\"\"",
        "event": {
            "action": "Approval",
            "kind": "event",
            "type": [
                "access"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "Approval",
            "action": "list"
        },
        "user": {
            "name": "QA_ADMIN"
        },
        "source": {
            "ip": "10.10.45.212",
            "address": "10.10.45.212"
        },
        "related": {
            "ip": [
                "10.10.45.212"
            ],
            "user": [
                "QA_ADMIN"
            ]
        }
    }
    	
	```


=== "wabaudit_action_list_type_sessionlog.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"list\" type=\"sessionlog\" user=\"OPERATOR\" client_ip=\"127.0.0.1\" infos=\"Current sessions\"",
        "event": {
            "action": "sessionlog",
            "reason": "Current sessions",
            "kind": "event",
            "category": "authentication",
            "type": [
                "access"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "sessionlog",
            "action": "list"
        },
        "user": {
            "name": "OPERATOR"
        },
        "source": {
            "ip": "127.0.0.1",
            "address": "127.0.0.1"
        },
        "related": {
            "ip": [
                "127.0.0.1"
            ],
            "user": [
                "OPERATOR"
            ]
        }
    }
    	
	```


=== "wabaudit_action_restore_type_backup_restore.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"restore\" type=\"Backup/Restore\" user=\"admin\" client_ip=\"192.168.0.12\" infos=\"Backup ['wab-6.0-cspn_2019-02-04_16-59-11.wbk' restored]\"",
        "event": {
            "action": "Backup/Restore",
            "reason": "Backup ['wab-6.0-cspn_2019-02-04_16-59-11.wbk' restored]",
            "kind": "event",
            "category": "database",
            "provider": "wabengine"
        },
        "wallix": {
            "type": "Backup/Restore",
            "action": "restore"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "192.168.0.12",
            "address": "192.168.0.12"
        },
        "related": {
            "ip": [
                "192.168.0.12"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabaudit_approvals.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"list\" type=\"Approvals\" user=\"OPERATOR\" client_ip=\"127.0.0.1\" infos=\"\"\n",
        "event": {
            "action": "Approvals",
            "reason": "\"\"\n",
            "kind": "event",
            "type": [
                "access"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "Approvals",
            "action": "list"
        },
        "user": {
            "name": "OPERATOR"
        },
        "source": {
            "ip": "127.0.0.1",
            "address": "127.0.0.1"
        },
        "related": {
            "ip": [
                "127.0.0.1"
            ],
            "user": [
                "OPERATOR"
            ]
        }
    }
    	
	```


=== "wabauth.json"

    ```json
	
    {
        "message": "[wabauth] action=\"authentify\" user=\"admin\" client_ip=\"1.1.1.1\" status=\"success\" infos=\"diagnostic [Authentication success: identified with local(LOCAL), authentified with: API key Bastion(APIKEY).]\"",
        "event": {
            "reason": "diagnostic [Authentication success: identified with local(LOCAL), authentified with: API key Bastion(APIKEY).]",
            "kind": "event",
            "category": "authentication"
        },
        "wallix": {
            "action": "authentify"
        },
        "user": {
            "name": "admin"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "wabengine_authentify.json"

    ```json
	
    {
        "message": "action=\"authentify\" user=\"username123\" client_ip=\"1.1.1.1\" status=\"failure\" infos=\"diagnostic [Authentication failed]",
        "event": {
            "reason": "\"diagnostic [Authentication failed]",
            "kind": "event",
            "category": "authentication",
            "type": [
                "denied"
            ]
        },
        "wallix": {
            "action": "authentify"
        },
        "user": {
            "name": "username123"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ],
            "user": [
                "username123"
            ]
        }
    }
    	
	```


=== "wabengine_sessionlog.json"

    ```json
	
    {
        "message": "[wabaudit] action=\"list\" type=\"sessionlog\" user=\"OPERATOR\" client_ip=\"127.0.0.1\" infos=\"Closed sessions, Sessionlogs newly terminated\"\n",
        "event": {
            "action": "sessionlog",
            "reason": "\"Closed sessions, Sessionlogs newly terminated\"\n",
            "kind": "event",
            "category": "authentication",
            "type": [
                "end"
            ],
            "provider": "wabengine"
        },
        "wallix": {
            "type": "sessionlog",
            "action": "list"
        },
        "user": {
            "name": "OPERATOR"
        },
        "source": {
            "ip": "127.0.0.1",
            "address": "127.0.0.1"
        },
        "related": {
            "ip": [
                "127.0.0.1"
            ],
            "user": [
                "OPERATOR"
            ]
        }
    }
    	
	```


=== "wbauth_authentify.json"

    ```json
	
    {
        "message": "[wabauth] action=\"authentify\" user=\"username123\" client_ip=\"1.1.1.1\" status=\"failure\" infos=\"diagnostic [Authentication failed]",
        "event": {
            "reason": "\"diagnostic [Authentication failed]",
            "kind": "event",
            "category": "authentication",
            "type": [
                "denied"
            ]
        },
        "wallix": {
            "action": "authentify"
        },
        "user": {
            "name": "username123"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ],
            "user": [
                "username123"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`destination.ip` | `ip` | IP address of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.provider` | `keyword` | Source of the event. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`host.ip` | `ip` | Host ip addresses. |
|`process.command_line` | `wildcard` | Full command line that started the process. |
|`service.name` | `keyword` | Name of the service. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |
|`user.name` | `keyword` | Short name or login of the user. |

