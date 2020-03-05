In order to **Graphia** data must be imported in the correct format. A
wide range standard and non-standard file formats are available for data
input (see below).

### Numerical Data Input (for correlation analyses)

#### Numerical Matrix (.csv)

![Data_file_format.png](Data_file_format.png "Data_file_format.png")
Data input format for generating **correlation graphs** within
**Graphia**. Files need to be saved as comma separated files (.csv)

**Graphia** can create a graph structure by calculating a correlation
matrix from any numerical data table. In this context nodes represent
entities for which there is a range of data variables that describe the
behaviour of the entity and edges represent correlations between them.
Data tables can be big, i.e. many thousands of rows and columns, and can
be supplemented with with other information (attribute data), which
relate to known properties of the entities represented in the table.
Graphs generated are weighted, non-directional networks.

A **correlation-ready data file** consists of numerical values arranged
in rows and columns (see figure). Each **entity** (variable) is
represented by a row, the first column entry being the entity's (node's)
ID. Following the entity ID column, there is the option to add node
attribute data (light blue columns). This may be numerical or
non-numerical information relating to the entities. These are not used
to generate the graph but can be used to understand its structure
through visualisation and enrichment analysis etc. Ideally, the final
attribute column should be non-numerical so as not to confuse the data
parser. Similarly, information relating to the columns of data can be
added below the column ID row. Following attribute data (where
available), is the data table which will be used by the program to
generate the correlation matrix. Each cell within the entity row
represents a measured variable for that entity. Numerical data columns
that would should be arranged together to form a contiguous matrix.
Correlation analysis will only be performed on the contiguous numerical
section. To aid interpretation of the result graph, it is highly
desirable to order columns (possibly rows) into logical groupings, i.e.
based on their attributes.

It should be noted that when loading data, an option is available to
**transpose the matrix**, thereby allowing the user to examine the
similarity between columns, as opposed to rows.

[Click here for a **detailed guide to correlation analysis using a
numerical matrix**](Graphia:Correlation_Analysis "wikilink").

### Graph-Based

#### Adjacency Matrix (.csv, .tsv)

**Graphia** can open **[adjacency
matrices](wikipedia:Adjacency_matrix "wikilink")** with tab or comma
separators, with the file extension .csv, or .tsv.

Matrices of **similarity measures** calculated by whatever method
appropriate and saved as .csv file can be loaded directly into
**Graphia**. On import use drop-down menu to specify **Matrix CSV
File.**

`   A   B   C   D   E   F   G   H   I   J`
`A  1.00    0.93    0.92    0.91    0.91    0.90    0.91    0.91    0.90    0.88`
`B  0.93    1.00    0.91    0.91    0.90    0.90    0.90    0.90    0.90    0.87`
`C  0.92    0.91    1.00    0.95    0.94    0.93    0.92    0.92    0.92    0.90`
`D  0.91    0.91    0.95    1.00    0.93    0.93    0.92    0.92    0.92    0.89`
`E  0.91    0.90    0.94    0.93    1.00    0.93    0.92    0.92    0.92    0.90`
`F  0.90    0.90    0.93    0.93    0.93    1.00    0.90    0.90    0.90    0.87`
`G  0.91    0.90    0.92    0.92    0.92    0.90    1.00    0.92    0.91    0.89`
`H  0.91    0.90    0.92    0.92    0.92    0.90    0.92    1.00    0.91    0.89`
`I  0.90    0.90    0.92    0.92    0.92    0.90    0.91    0.91    1.00    0.90`
`J  0.88    0.87    0.90    0.89    0.90    0.87    0.89    0.89    0.90    1.00`

A graph can be represented using a matrix, where each row and column
reflects a node and each (non-zero) value represents an edge. The
following matrix represents a graph with 5 nodes and 6 edges of edge
weight 1.

`0,1,0,0,0`
`0,0,0,1,0`
`0,1,0,0,1`
`0,0,1,0,0`
`1,0,0,0,0`

The matrix can (should) also optionally include node names, in this case
A-E.

`,A,B,C,D,E`
`A,0,1,0,0,0`
`B,0,0,0,1,0`
`C,0,1,0,0,1`
`D,0,0,1,0,0`
`E,1,0,0,0,0`

Be sure to escape long names with quotes (spaces may be interpreted as
the end of name), a second set of node names is optional, for example:

`"Node One","Node Two","Node Three","Node Four","Node Five"`
`0,1,0,0,0`
`0,0,0,1,0`
`0,1,0,0,1`
`0,0,1,0,0`
`1,0,0,0,0`

#### Pairwise formats (.txt)

The simplest Graph format Graphia supports is pairwise.

Pairwise format is a simple way to define a graph. Each line represents
an edge. There is no support for additional attributes.

The following pairwise example will create a graph with two edges. NodeA
-\> Node B -\> NodeC. Edge direction is inferred from the order, i.e.
column 1 to column 2.

`NodeA NodeB`
`NodeB NodeC`

Node names can be escaped with quotes to allow for spaces, however
easiest option is to **avoid the use of spaces**.

Pairwise format optionally allows for an **edge weight** to be defined
(column 3).

`"Node A" "Node B" 2.3`
`"Node B" "Node C" 1.5`
`"Node A" "Node C" 0.5`

#### Biolayout (.layout)

**Layout files** can be used as a simple means to load node/edge and
attribute data into Graphia. This is a simple but non-standard file
format originally used by BioLayout *Express*<sup>3D</sup> and still
used by **Graphia Pro** to import and export graphs. It is essentially a
**.txt** file with the extension being changed to **.layout** such that
Graphia's parsers know what format to expect.

In the example below taken from an analysis of name use over time, names
and the correlation between their use profile defines the connections in
a weighted edge graph. The //NODECLASS assignments define known
attributes associated with those names: Column1: **//NODECLASS**,
Column2: **NodeID**, Column3: **Attribute value**, Column4: **Attribute
class**. In this example there are three 'classes' of attribute data
(for two names only) that define the gender assignment of the name,
number of years in use and year it was first recorded.

`"Karon"       "Lora"   0.992296`
`"Clara"       "Marilyn"    0.9800304`
`"Karon"       "Marilyn"    0.9901779`
`"Karla"       "Marilyn"    0.98446643`
`"Karla"       "Lora"       0.9803633`
`"Lora"    "Marilyn"    0.98961353`
`"Brigid"   "Mavis" 0.9937161`
`"Marilyn"  "Mavis" 0.981609`
`"Mavis"       "Rosehannah" 0.99082536`
`"Brigid"   "Denice"    0.9808063`
`"Denice"   "Mavis" 0.98275685`
`"Brigid"   "Rosehannah"    0.9859566`
`//NODECLASS     "Lora" "F" "Sex"`
`//NODECLASS    "Lora"  "95"    "No. of years in use"`
`//NODECLASS    "Lora"  "1839"  "Year of first recorded use"`
`//NODECLASS    "Karon" "F" "Sex"`
`//NODECLASS    "Karon" "38"    "No. of years in use"`
`//NODECLASS    "Karon" "1839"  "Year of first recorded use"`

#### BioPAX OWL ontology (.owl)

Biological Pathway Exchange (**[BioPAX](wikipedia:BioPAX "wikilink")**)
is a standard format for sharing biological pathway structures, based on
the OWL format. Graphia enterprise supports **[BioPax
Level 3](http://www.biopax.org/release/biopax-level3-documentation.pdf)**
OWL files.

There are a large number of biological pathways documented online, such
those stored in **[Reactome](https://reactome.org/)**.

Graphia will create a node for entity within the pathway and an edge for
a relationship between them.

**Examples of nodes:** DNA, RNA, Protein, Gene, BiochemicalReaction etc.

**Examples of edges:** pathwayComponent, memberPhysicalEntity,
controller, controlled, product. etc.

#### JSON Graph (.json)

JSON Graph is a specification for the definition of graphs utilising the
widely popular JSON format.

Graphia can load JSON Graph based graphs.

An example [**JSON Graph**](http://jsongraphformat.info/) connecting
nodes A to B looks like the following:

`{`
`    "graph": {`
`        "nodes": [`
`            {`
`                "id": "A",`
`            },`
`            {`
`                "id": "B",`
`            }`
`        ],`
`        "edges": [`
`            {`
`                "source": "A",`
`                "target": "B"`
`            }`
`        ]`
`    }`
`}`

Node and Edge attributes can be represented inside definitions through
the use of a **metadata** object

`{`
`    "graph": {`
`        "nodes": [`
`            {`
`                "id": "A",`
`                "metadata": `
`                {`
`                   "A Node Attribute": "Some Value",`
`                   "Another Node Attribute": "Some other Value"`
`                },`
`            },`
`            {`
`                "id": "B",`
`            }`
`        ],`
`        "edges": [`
`            {`
`                "source": "A",`
`                "target": "B"`
`            }`
`        ]`
`    }`
`}`

Ensure that all values are surrounded in quotes in order to be JSON
Graph compliant.

#### GraphML (.graphml)

Graphia supports the loading of
**[GraphML](http://graphml.graphdrawing.org/)** files, an XML-style
graph file format.

The following is a simple example of GraphML with two nodes and edges:

<graphml>
`    `<graph id="G" edgedefault="directed">
`        `<node id="n0"/>
`        `<node id="n1"/>
`        `<edge source="n0" target="n2"/>
`        `<edge source="n1" target="n2"/>
`    `</graph>
</graphml>

To set a node name use the **desc** tag, this is the preferred way in
Graphia Enterprise and follows the GraphML specification.

<graphml>
`    `<graph id="G" edgedefault="directed">
`        `<node id="n0">
`             `<desc>`Node One`</desc>
`        `</node>
`        `<node id="n1">
`             `<desc>`Node Two`</desc>
`        `</node>
`        `<edge source="n0" target="n2"/>
`        `<edge source="n1" target="n2"/>
`    `</graph>
</graphml>

In order to add additional node and edge attributes to a GraphML file,
they have be declared as a **key** first. Once the **key** is declared
you can set the value for the edge using a **data tag** and the relevant
id.

<graphml>
`    `<graph id="G" edgedefault="directed">
`        <key id="d0" attr.name="Attribute Name" attr.type="string" for="node"/>`
`        `<node id="n0">
`            <data key="d0">Some attribute value</data>`
`        `</node>
`        `<node id="n1">
`            <data key="d0">Some other attribute value</data>`
`        `</node>
`        `<edge source="n0" target="n2"/>
`        `<edge source="n1" target="n2"/>
`    `</graph>
</graphml>

#### Graph Modelling Language (.gml)

Graphia can load
**[GML](wikipedia:Graph_Modelling_Language "wikilink")** files, a
hierarchical text format similar to a simplified JSON.

Here is a simple example of a GML file, where two nodes are connected
via an edge.

`graph`
`[`
`    node`
`    [`
`        id 0`
`        label "Node One"`
`    ]`
`    node`
`    [`
`        id 1`
`        label "Node Two"`
`    ]`
`    edge`
`    [`
`        source 0`
`        target 1`
`    ]`
`]`

Additional attributes can be added as key-value pairs. The key name
**must** be alphanumeric and contain no spaces or punctuation. Keys must
begin with an non-number character. String values should be escaped with
double quotes. Strings that contain special characters should be HTML
encoded

`graph`
`[`
`    node`
`    [`
`        id 0`
`        label "Invalid"`
`        // 1_invalid_key is invalid due to punctuation and numeric first character!`
`        1_invalid_key "Some Value" `
`    ]`
`    node`
`    [`
`        id 1`
`        label "Node Two"`
`        validKey "Some Value" // This key is correct`
`    ]`
`]`

More information on **GML** can be found
**[here](https://www.fim.uni-passau.de/fileadmin/files/lehrstuhl/brandenburg/projekte/gml/gml-technical-report.pdf)**.

#### MATLAB Data file (.mat)

**Graphia** supports loading of 2D adjacency matrix/array variables
exported from
[**MATLAB**](https://uk.mathworks.com/products/matlab.html).