
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Application Logs` | This tool forward application logs to your SIEM. |
| `Web Logs` | This tool forward application logs to your SIEM. |
| `Network device Logs` | This tool forward application logs to your SIEM. |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `host` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "input.json"

    ```json
	
    {
        "message": "CEF:1|Panda Security|paps|02.45.00.0000|registryc|registryc|1|Client=1212122 Date=2018-09-27 02:26:52.200188 MachineName=DESKTOP-PC MachineIP=192.168.0.11 User=NT AUTHORITY\\SYSTEM MUID=713FC2B45B429J291EB53467357AC1B7 Op=CreateExeKey Hash=C86854DF4F3AEC59D523DBAD1F5031FD DriveType=Fixed Path=SYSTEMX86|\\CompatTelRunner.exe ValidSig=true Company=Microsoft Corporation Broken=true ImageType=EXE 32 ExeType=Unknown Prevalence=Medium PrevLastDay=Low Cat=Goodware MWName= TargetPath=3|PROGRAM_FILESX86|\\Windows Defender\\MsMpeng.exe RegKey=\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\WicaAvPathsExpiredTemp?0",
        "event": {
            "kind": "event",
            "category": [
                "host"
            ],
            "type": [
                "info"
            ]
        },
        "siemfeeder": {
            "RegKey": "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\WicaAvPathsExpiredTemp?0",
            "TargetPath": "3|PROGRAM_FILESX86|\\Windows Defender\\MsMpeng.exe",
            "Cat": "Goodware",
            "PrevLastDay": "Low",
            "Prevalence": "Medium",
            "ExeType": "Unknown",
            "ImageType": "EXE 32",
            "Broken": "true",
            "Company": "Microsoft Corporation",
            "ValidSig": "true",
            "Path": "SYSTEMX86|\\CompatTelRunner.exe",
            "DriveType": "Fixed",
            "Hash": "C86854DF4F3AEC59D523DBAD1F5031FD",
            "Op": "CreateExeKey",
            "MUID": "713FC2B45B429J291EB53467357AC1B7",
            "User": "NT AUTHORITY\\SYSTEM",
            "MachineIP": "192.168.0.11",
            "MachineName": "DESKTOP-PC",
            "Date": "2018-09-27 02:26:52.200188",
            "Client": "1212122"
        },
        "host": {
            "name": "DESKTOP-PC",
            "id": "713FC2B45B429J291EB53467357AC1B7"
        },
        "source": {
            "ip": "192.168.0.11",
            "address": "192.168.0.11"
        },
        "user": {
            "name": "NT AUTHORITY\\SYSTEM"
        },
        "registry": {
            "key": "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\WicaAvPathsExpiredTemp?0"
        },
        "related": {
            "ip": [
                "192.168.0.11"
            ],
            "user": [
                "NT AUTHORITY\\SYSTEM"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`host.id` | `keyword` | Unique host id. |
|`host.name` | `keyword` | Name of the host. |
|`registry.key` | `keyword` | Hive-relative path of keys. |
|`registry.path` | `keyword` | Full path, including hive, key and value |
|`source.ip` | `ip` | IP address of the source. |
|`user.name` | `keyword` | Short name or login of the user. |

