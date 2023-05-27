# What is Rodeo

## Overview

Rodeo is a data ingestion tool designed to process, transform, and send data to graph databases. Rodeo currently supports the [Neo4j](https://neo4j.com/) database. The purpose of this tool is to provide users with a method to easily define a graph schema, process data of various formats, and enrich the data as it is transformed into nodes and relationships. Rodeo provides these capabilities through its use of mapping files where users can model their data. Rodeo also provides a plugin architecture that allows users to create and utilize custom plugins to transform data at various points in the processing pipeline.

## How It Works

Rodeo is composed of two separate components, `rodeo-service` and `rodeo`. The `rodeo-service` is responsible for the processing, enriching, and shipping of the user data. It will typically be a service that is always running in the background. The `rodeo` program is a command line interface (CLI) and shell that communicates with the `rodeo-service`. This will be the primary way users will interact with the Rodeo system and send commands to the `rodeo-service`. As mentioned earlier, the `rodeo` program acts as both a CLI and a Shell depending on how it is executed. If commands and flags are passed to the program then it will function as a CLI and will immediately run the provided commands. If no command or flag is passed, then it will start the Rodeo Shell.
