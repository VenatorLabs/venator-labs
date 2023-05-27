# Configuration

The `rodeo-service` starts with a default configuration if a configuration file is not provided on launch. You can learn more about providing a configuration file at launch on the Venator Labs wiki. [Wiki - Configuration](https://github.com/VenatorLabs/venator-labs/wiki/Rodeo-Documentation#providing-a-configuration-file-on-launch). Otherwise, the `rodeo-service` can be configured by passing it a configuration via the CLI/Shell `set-config` command.

## Configuration Files

Rodeo utilizes a YAML based configuration file to store the relevant preferences and connection information. A template configuration file has been provided below with each field labeled with a description type.

```yaml
# general rodeo options
debug: bool, do you want more verbose debug logs?
logToFile: bool, do you want the service to log to a file?
logFilePath: string, optional, the path to the log file
# information for connecting to the database
dbType: string {neo4j}, name of the type of database to connect to
dbHost: string, hostname or ip address of database
dbUser: string, database username
dbPassword: string, database password
```