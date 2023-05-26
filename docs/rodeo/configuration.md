# Configuration

## Overview

Rodeo utilizes a YAML based configuration file to store the relevant preferences and connection information. A template configuration file should be provided with every distribution under the `templates` directory. Each field in the template should be labeled with a description and data type.

**Note:** Certain commands like `validate` and `list-plugins` do **NOT** require a configuration file to be provided in order to run properly.
