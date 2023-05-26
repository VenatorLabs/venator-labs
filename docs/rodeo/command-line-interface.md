# Command Line Interface

## Overview

Rodeo comes with a simple command line interface (CLI) for users to interact with. The CLI can be used by executing one of the startup scripts rodeo (*nix) or rodeo.bat (windows) located in the bin folder of the distribution. Executing either script with the -h or --help flag will display all possible commands and flags. The following sections will describe the available flags and commands and how to use them.

## Flags

`-c --configuration <path>`: Specify a configuration file for Rodeo to use, this
flag should be followed with a file name or path to a valid Rodeo configuration
file.

`-p --plugin-directory <dir>`: Specify the plugin directory Rodeo will load
from, this should be followed by a directory name or path to a directory.

`-h --help`: Display help for Rodeo or a specific Rodeo command.

`-V --version`: Display the current version of the Rodeo tool.

`--json=<json_data_file>`: Used to pass in a JSON data file to the ingest
command. Use mutliple times to pass in multiple JSON data files.

`--csv=<json_data_file>`: Used to pass in a CSV data file to the ingest command.
Use mutliple times to pass in multiple CSV data files.

`-m=<mapping_file> --mapping=<mapping_file>`: Used to pass in a mapping file to
the ingest command. Use multiple times to passin multiple data files.

## Commands

### validate

The `validate` command is used to validate the format of a mapping file before
using it to process or ingest a data source. Using this command will result in
Rodeo displaying error logs for any syntax errors detected within the specified
mapping files.

#### Example

```sh
./bin/rodeo validate example-mapping.yml
```

### ingest

The `ingest` command is used to process one or more data files using a specified
mapping file. After processing the data, Rodeo will attempt to send it to either
a database specified in a configuration file or a database located on the
localhost at the default Neo4j bolt protocol port.

#### Example: No Configuration

```sh
./bin/rodeo ingest --json=example-data-1.json -m=example-mapping.yml
```

#### Example: With Configuration

```sh
./bin/rodeo -c example-config.yml ingest --json=example-data-1.json -m=example-mapping.yml
```

### list-plugins

The `list-plugins` command will display the names of all Rodeo plugins that the
system is able to load along with their description.

#### Example: Default Directory

```sh
./bin/rodeo list-plugins
```

#### Example: Specified Directory

```sh
./bin/rodeo -p example-dir list-plugins
```