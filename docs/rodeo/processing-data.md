# Processing Data

Rodeo processes each individual row or line of information in a dataset into nodes and relationships. It does this by using a combination of user provided inputs in the form of mapping files and plugins.

### Mapping Files

Mapping files are core to the functionality of Rodeo. These YAML based files
represent the data fields and the schema in which the data will be entered into
the graph. A mapping file defines five primary things: fields, nodes,
relationships, indices, and plugins. Fields defines the key value pairs that is
contained within the data that is going to be processes. Nodes outlines how
those fields will be added to nodes as attributes as well as node labels and the
conditions under which it is created. Relationships list how the nodes will
relate to one another and also specifies a relationship's attributes and the
conditions under which it is created. Indices allows users to define node fields
and labels that will be used by the database for faster search. Finally,
plugins lists the plugins that the mapping file will use, if any. More
information and examples of mapping files can be found on the Venator Labs wiki.
[Wiki - Mapping Files](https://github.com/VenatorLabs/venator-labs/wiki/Rodeo-Documentation#mapping-files)

### Plugins

Rodeo has been designed to allow users to utilize custom plugins to manipulate,
transform, and enrich their data as it is processed into nodes and
relationships. A plugin has an opportunity to "hook" three parts of the
processing pipeline when the data is at various stages. The first is before any
processing has been done, when the data is still in its original form. The
second is just after the nodes have been generated from the document. The third
and final opportunity is after the relationships have been generated. If you
want to learn more about how plugins work and how to write your own you can find
more information on the Venator Labs wiki. [Wiki - Plugins](https://github.com/VenatorLabs/venator-labs/wiki/Rodeo-Documentation#plugins).