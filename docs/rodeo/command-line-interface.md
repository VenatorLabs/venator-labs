# Command Line Interface

## CLI and Shell Commands

Rodeo comes with a simple CLI and shell for users to interact with. Executing the program with the `-h` or `--help` flag will display all possible commands and flags.

### set-config

The `set-config` set the Rodeo service configuration via a configuration file.

**Example**

```sh
rodeo set-config path_to_config_file
```

### list-config

The `list-config` command lists out the current Rodeo service configuration information.

**Example**

```sh
rodeo list-config
```

### set-plugins

The `set-plugins` command allows you to change the directory the Rodeo service will look for plugins in.

**Example**

```sh
rodeo set-plugins path_to_plugins_directory
```

### list-plugins

The `list-plugins` command will display the names of all Rodeo plugins that the system is able to load along with their description.

**Example**

```sh
rodeo list-plugins
```

### reload-plugins

The `reload-plugins` command will cause the Rodeo service to uninstall all current plugins and install any plugins located in the specified plugins directory.

**Example**

```sh
rodeo reload-plugins
```

### validate

The `validate` command is used to validate the format of a mapping file before using it to process or ingest a data source. Using this command will result in Rodeo displaying error messages for any syntax errors detected within the specified mapping files.

**Example**

```sh
rodeo validate example-mapping.yml
```

### ingest

The `ingest` command is used to process one or more data files using a specified mapping file. After processing the data, Rodeo will attempt to send it to the database specified in a configuration file.

**Example**

```sh
rodeo ingest --json=example-data-1.json -m=example-mapping.yml
```

### start-watcher

The `start-watcher` command spins up a directory watching thread that will ingest data from any file placed into the directory that matches a specified regular expression pattern.

**Example**

```sh
rodeo start-watcher -m=example-mapping.yml /directory/to/watch example-data-.*.json JSON
```

### stop-watcher

The `stop-watcher` command allows you to shutdown a directory watcher thread based on its numeric id.

**Example**

```sh
rodeo stop-watcher 0
```

### list-watchers

The `list-watchers` command lists out all active directory watcher threads.

**Example**

```sh
rodeo list-watchers
```

### shutdown-service

The `shutdown-service` command will cause the Rodeo service to terminate.

**Example**

```sh
rodeo shutdown-service
```