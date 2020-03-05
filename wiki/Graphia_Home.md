![Graphia_UI.png](Graphia_UI.png "Graphia_UI.png")
![Coexpression_graph.png](Coexpression_graph.png
"Coexpression_graph.png")
![Phlyogenetic_tree_of_all_mammals.png](Phlyogenetic_tree_of_all_mammals.png
"Phlyogenetic_tree_of_all_mammals.png")**Graphia** is a powerful network
analysis platform **for big data exploration**. With support for massive
graphs, fast dynamic layout, beautiful 3D visualisations and **powerful
graph analytics,** it represents a new analysis paradigm.

Core to **Graphia’s** functionality is its ability to quickly go from
any data matrix to a relationship graph, where data structure can be
explored and analysed as a whole. It couples cutting-edge visualisation
technologies with the latest generation of graph analysis algorithms to
provide a highly **flexible interface** where data can be viewed,
manipulated and interpreted.
![RNA-seq_assembly_graph.png](RNA-seq_assembly_graph.png
"RNA-seq_assembly_graph.png") The platform works using a plugin system
and be **customised to meet your specific needs**. The pages below are
designed to help get you going and guide through **Graphia's rich and
powerful functionality.**

| [Use Case Examples](Graphia:Use_Case_Examples "wikilink") | [Tutorials](Graphia:Tutorials "wikilink") | [Input Formats](Graphia:Input_formats "wikilink") | [Example Datasets](https://kajeka.com/example-data/) | [Correlation Analysis](Graphia:Correlation_Analysis "wikilink") |
| --------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------- | ---------------------------------------------------- | --------------------------------------------------------------- |

See Also:

## Getting started:

### Requirements

**Graphia** is platform independent and runs on **Windows**, **MacOS**
or **Linux** operating systems.

While Graphia will run on any modern computer, for processing and
**displaying larger graphs** (\>5,000 nodes), it is recommended that a
dedicated graphics card is used, such as those available from
[NVidia](https://www.nvidia.com/) or [AMD](https://www.amd.com/).

In short, the bigger the graph you want to render, the better your
hardware configuration (CPU, RAM, GPU) will need to be for fast,
efficient layout and analysis.

### Installation

To download the software, please go to
**[Downloads](https://kajeka.com/graphia-download)** section and follow
instructions.

## Key concepts in network analysis:

### Nodes and Edges

**Graphs (networks)** can be used to represent many different types of
data. A graph can be considered as a sum of its nodes and edges:

  - **Nodes**, sometimes also called **vertices**, generally **represent
    different entities**. For example, people in a social network, or
    genes in a biological network. **Nodes** are generally visually
    represented by a circle or a sphere. Nodes can also be associated
    with different attribute data; properties about the the entity they
    represent. For example, if nodes in a graph represent people, the
    graph may have attributes for age and gender. A nodes **'degree**'
    is the number of edges associated with it. **Edges** convey
    information about **relationships between nodes**, and thus the
    entities they represent. These could be physical contacts,
    transactions, calculated similarities etc.. There are various types
    of edges:
      - **Directed edges** imply a one way relationship, for example
        person A called person B, but not the other way round, or
        protein A phosphorylates protein B but the opposite does not
        happen.
      - **Undirected edges** depict commutative relationships between
        the nodes, in other words, A is related to B and B is also
        related to A.
      - **Weighted edges** can be directed or undirected and have a
        quantitative value associated with them. This is used to depict
        concepts such as reliability, strength of association or number
        of interactions.

<File:Directed> edge.png|Directed edge <File:Undirected>
edge.png|Undirected edge <File:Weighted> edge.png|Weighted undirected
edge

### Graph Topology and Metrics

A graph’s **structure** or
‘**[topology](wikipedia:Network_topology "wikilink")**’ is dependent
on the source of data it represents. A graph is a powerful visual
representation of the underlying structure of the data it represents. It
can be exploited to using analytical techniques to group nodes, for
example by using clustering, or by finding highly connected nodes.
Common graph metrics that describe either a graphs structure or a node's
properties within the graph include
[PageRank](wikipedia:PageRank "wikilink"),
[distance](wikipedia:Distance_\(graph_theory\) "wikilink"),
[betweeness](wikipedia:Betweenness_centrality "wikilink") and
[centrality](wikipedia:Centrality "wikilink").

A
**[component](wikipedia:Connected_component_\(graph_theory\) "wikilink")**
is a subset of a graph in which any two nodes are connected by following
a sequence of one or more edges. In other words, if nodes are not
connected in this way, they are in separate components.

[File:Sierpinski.png|Sierpinski](File:Sierpinski.png%7CSierpinski) Graph
[File:Grid.png|Grid](File:Grid.png%7CGrid) Graph <File:Tree>
graph.png|Tree Graph <File:Multi-component> graph.png|Multi-Component
Graph [File:Random.png|Random](File:Random.png%7CRandom) Graph
<File:Scale> free (PPI) Graph.png|Scale-free Graph (PPI network)
<File:Time-course> graph.png|Time-course Graph (correlation matrix)
<File:Structered> correlation graph.png|Structured Graph (correlation
matrix) <File:Overlap> Graph (DNA assembly)2.png|Overlap Graph (DNA
assembly)

### Attributes

**Attribute data** refers to information associated with a node or edge.
For example, in the case where a node represents a person, it could
refer to their gender, ethnicity or socioeconomic status. Attributes can
also be calculated based on the graph itself, for example node degree,
PageRank or cluster membership.

Attribute values may be used as a basis for visualisation. For example,
a numerical attribute's value may be used to scale a node, or in the
case where the attribute has a textual value, it can be used to assign a
discrete colour.

The graph can also be queried using an attribute's value. For example,
by searching a graph for all the nodes that represent men. Attribute
data can also be used for analyses - if a cluster of nodes seems to have
a lot of men in it, is it statistically enriched in them.

In **Graphia** attribute data can be loaded using a number of file
formats, and can be examined in the **'attribute viewer**'.

### Layout

**[Graph layout](wikipedia:Graph_drawing "wikilink")** is performed by a
‘layout algorithm’ whose job is position nodes and edges according to a
set of defined mathematical rules or forces. The purpose of a layout
algorithm is to allow the person viewing the graph to understand a
graph's structure at a local or global level. There a number of
different types of algorithm, some better suited than others to
particular graph topologies.

**[Force-directed graph
layout](wikipedia:Force-directed_graph_drawing "wikilink")** is a class
of graph layout algorithms that calculate the positions of each node by
simulating an attractive force between each pair of linked nodes, as
well as a repulsive force between the nodes. Typically, the **attractive
force acts like a spring** between the nodes, calculated using [Hooke’s
law](wikipedia:Hooke's_law "wikilink"). On the other hand, two nodes are
pushed away from each other using [Coulomb’s
law](wikipedia:Coulomb's_law "wikilink"). **Graphia** uses its own
force-directed dynamic layout algorithm to position nodes in 3D space.
It runs continually (unless paused) and seeks to place nodes in their
optimal position for visualisation. This means should nodes or edges be
added or removed, the graph's layout will adjust accordingly. The
parameters for layout can be changed on the fly, thereby adjusting the
appearance of graph to suit an individual’s preference.

### Transformation

Graph **transformation** is a process by which a graph is modified to
produce a new graph, or create new attribute(s). It is central to
**Graphia's** core functionality. Transforms include such processes as a
simple edge filter, whereby weighted edges below a certain threshold are
removed, or branch pruning algorithms where a graph is reduced to only
include cycles. **Graphia** has a sophisticated and flexible interface
for transforming graphs on-the-fly.

### Visualisation

Graphs are an inherently visual medium with which to explore data,
allowing one to understand data structure at a global or local level.
However, they can also be used as a medium on which other data can be
overlaid and explored visually. Text can by overlaid on a graph,
providing the names of nodes or the weight of an edge. **Colour**,
**shape** and **size** can also be used to visually distinguish between
nodes and edges with different properties, potentially enriching any
**graph** **visualisation**.

**Graphia** possesses a sophisticated and flexible interface for
visualising graph data.
![Pearson_distribution.png](Pearson_distribution.png
"Pearson_distribution.png")

### Correlation analysis

**Correlation analysis** is a method of statistical evaluation used to
study the strength of a relationship between two continuous variables.
This particular type of analysis is useful when an analyst wants to
establish if there are possible relationships between variables. It is
applicable to a wide variety of data types, from share prices to gene
expression data; in fact any numerical matrix, *the* *bigger the
better*.

If **correlation** is found between two variables it means that when
there is a systematic change in one variable, there is also a systematic
change in the other; the variables alter together over time or in
individual sets of measurements. Correlations can be either **positive**
or **negative**.

  - **Positive correlation** exists if one variable increases
    simultaneously with the other, i.e. the high numerical values of one
    variable relate to the high numerical values of the other.

<!-- end list -->

  - **Negative correlation** exists if one variable decreases when the
    other increases, i.e. the high numerical values of one variable
    relate to the low numerical values of the other.

However, it should be noted that **correlation is not causation**,
because other variables (not measured) may have impacted on the results.

**Graphia** relies on the [**Pearson correlation
coefficient**](wikipedia:Pearson_correlation_coefficient "wikilink") for
graph-based analyses of numerical data. Pearson correlation measurements
range between +1 and -1. +1 indicates the strongest positive correlation
possible, and -1 indicates the strongest negative correlation possible.
Therefore the closer the coefficient to either of these numbers the
stronger the correlation of the data it represents. On this scale 0
indicates no correlation, hence values closer to zero highlight
weaker/poorer correlation than those closer to +1/-1. When using
correlation as a basis for **graph analyses** the use of a **threshold
value** selects statistically significant relationships (edges) whilst
excluding those that occur by random chance. It should be noted the
**narrower the data set**, i.e. number of points over which a variable
is measured, the more likely things are to be **correlated by chance**.
Calculating a correlation graph is a computationally intensive process
that grows quadratically (**n²**) with the number of data rows. It can
be a very big calculation and **Graphia** is designed to make this
**easy and fast** for large **high dimensional datasets**.

[Click here for a **detailed guide to correlation analysis using a
numerical matrix**](Graphia:Correlation_Analysis "wikilink").

In principle other [**correlation
measures**](wikipedia:Correlation_coefficient "wikilink") could be
employed for graph-based analyses.

### Cluster Analysis

**Cluster analysis** or **clustering** is the task of dividing a
collection into discrete groups of related objects, which are referred
to as **clusters**. In the graph based case, clusters form groups of
**nodes**. It is a main task of exploratory data mining, and a common
approach used in many fields for pattern finding. Cluster analysis
refers to the general task to be solved, not a specific algorithm. In
the context of a graph, the aim is define these clusters based on the
prevalence of high connectivity, which infers a degree of similarity.
The parameters of a clustering algorithm can generally be modified so
that clustering is more or less granular. Once defined clusters can also
be explored for their **enrichment** of nodes with a particular
attribute.

## Tutorials

### In tool tutorial

The first you open **Graphia,** the tool will run a brief tutorial to
provide a new user with the basic functionality.

Once closed you may reopen the tutorial by going to the menu **Help -\>
Show Tutorial**

### Video tutorials

[View our introductory video tutorial series
here](Graphia:Tutorials "wikilink")

  -
## Input formats

**For a detailed look at Graphia input formats and how to load them
please [view the dedicated input formats
page](Graphia:Input_formats "wikilink")**

In order to use **Graphia**, data must be imported in the correct
format. A wide range of standard and non-standard file formats are
available for data input:

### [Numerical Matrix (.csv, .tsv)](Graphia:Input_formats#Numerical_Data_Input_.28for_correlation_analyses.29 "wikilink")

[Click here for a detailed guide to correlation analysis using a
numerical matrix](Graphia:Correlation_Analysis "wikilink")

**Graphia** can create a graph structure by calculating a correlation
matrix from a numerical data table.

### [Adjacency Matrix (.csv, .tsv)](Graphia:Input_formats#Adjacency_Matrix_.28.matrix.2C_.csv.2C_.tsv.29 "wikilink")

**Graphia** can open matrices where cells are separated by tab or comma.
The file extension should be either .csv, or .tsv.

Matrices of **similarity measures** calculated by whatever method
appropriate and saved as .csv file can be loaded directly into
**Graphia**. On import, specify **Matrix CSV File** when prompted.

### [Pairwise formats (.txt)](Graphia:Input_formats#Pairwise_formats_.28.txt.29 "wikilink")

The simplest graph format **Graphia** supports is pairwise text.

Pairwise text format is very simple way to define a graph. Each line
specifies two node names that will be connected by an edge. There is no
support for additional attributes.

### [Biolayout (.layout)](Graphia:Input_formats#Biolayout_.28.layout.29 "wikilink")

This is a simple but non-standard file format originally used by
BioLayout *Express*<sup>3D</sup> and still used by Graphia Pro to import
and export graphs.

### [BioPAX OWL ontology (.owl)](Graphia:Input_formats#BioPAX_OWL_ontology_.28.owl.29 "wikilink")

Biological Pathway Exchange ([**BioPAX**](wikipedia:BioPAX "wikilink"))
is a standard format for sharing biological pathway structures, based on
the OWL format. Graphia enterprise supports **BioPax Level 3** OWL
files.

### [JSON Graph (.json)](Graphia:Input_formats#JSON_Graph_.28.json.29 "wikilink")

[JSON Graph](https://github.com/jsongraph/json-graph-specification) is a
specification for the definition of Graphs utilising the widely popular
JSON format.

### [GraphML (.graphml)](Graphia:Input_formats#GraphML_.28.graphml.29 "wikilink")

[**GraphML**](http://graphml.graphdrawing.org/) is an XML-style graph
format. Graphia supports the loading of GraphML files.

### [Graph Modelling Language (.gml)](Graphia:Input_formats#Graph_Modelling_Language_.28.gml.29 "wikilink")

[GML](wikipedia:Graph_Modelling_Language "wikilink") is a hierarchical
text format similar to a simplified JSON. Graphia can load GML files.

### [MATLAB Data file (.mat)](Graphia:Input_formats#MATLAB_Data_file_.28.mat.29 "wikilink")

Graphia Enterprise supports loading 2D adjacency matrix/array variables
exported from MATLAB.

**For a detailed look at Graphia input formats and how to load them
please [view the dedicated input formats
page](Graphia:Input_formats "wikilink")**

## Example data

Go to our **[Example Data](https://kajeka.com/example-data/)** page.

## Functions

### Layout

![Graph_Layout_Menu.png](Graph_Layout_Menu.png
"Graph_Layout_Menu.png") The layout algorithm in the **Graphia** uses a
force-directed algorithm to dynamically position nodes within the graph.
A limit is set on the distribution of forces within the graph to
determine when the graph is at a minima. Some graphs never reach a
stable-minima and will eventually stop laying out once **Graphia** has
detected no change over a large time period. Once a suitable minima has
been detected, it is not possible to restart the layout without
modifying the structure of the graph. When the graph structure is
changed, due the removal or addition of node(s) or edges, i.e. undergone
a transformation, layout will resume.

To **Pause** and **Resume** the layout use the "Pause" key.

To change the force model for layout go to **Layout -\> Settings** and
use **Local** or **Global** sliders (bottom left of graph window) to
dynamically change appearance of a graph

### Navigation

Once a file has been loaded into **Graphia** the network graph will be
displayed.

*To:*

  - ![Graphia_UI_-_annotated.png](Graphia_UI_-_annotated.png
    "Graphia_UI_-_annotated.png")**Rotate** the graph, press the left
    mouse button and drag.
  - **Translate** the graph (move up, down, left, right), press right
    mouse and drag.
  - **Zoom** in or out, rotate mouse wheel.
  - **Focus** on a specific node, double click it.
  - **Select Single Nodes** in the graph, press left mouse button on
    node.
  - **Select Multiple Nodes** in the graph, press and hold Shift, then
    drag a selection rectangle around nodes.
  - **View a Component** (multi-component graphs only) double click left
    mouse button on a node in the component of interest.
  - **Exit Component Mode** and to return to overview mode, click the
    back arrow at the bottom of the screen.
  - **Delete node(s)** by selecting them as above, then click the delete
    icon in the toolbar.

### Setting visual preferences

The **Options** dialog (accessible from the **Edit** menu) allows the
user to change various defaults in accordance with their preferences.

The **Appearance** tab allows a user to change the default sizes and
colours of various graph elements, and the font used on the main graph
display.

The **Transition Time** slider determines how quickly a graph will
transform from one state to another and **Minimum Component Radius**
alters the relative size of components in a multi-component graph
layout.

The **Misc** tab contains other unrelated options. If **Focus Found
Nodes** is checked **Graphia** will move the display to focus on the
result of a find operation. If **Switch To Component Mode when Finding**
is selected, the containing component of the find result will be
automatically focused. **Web Search Url** allows the user to customise
the website that is opened when right clicking a node and selecting
*Search Web*. In this context, %1 is substituted for the selected node
name(s). **Maximum Undo Levels** refers to the number of steps that can
be reversed by clicking on the undo button. Using a smaller value will
reduce the amount of memory used, at the expense of some flexibility in
how far back changes can be undone.

We provide help within the tool but an experienced user may wish to
**Disable Extended Help Tooltips**.

### Search

There are three ways to search:

1.  **Find (Ctrl+F):** Search the graph's node attributes for some term.
2.  **Advanced Find (Ctrl+Shift+F)**: Search the graph for a term within
    a specific attribute.
3.  **Find By Attribute Value (Ctrl+H)**: Select nodes where an
    attribute has a specific value.

When node(s) match the search term they will be highlighted in the
graph.

### Transformation Options

![Transformation_Menu2.png](Transformation_Menu2.png
"Transformation_Menu2.png") **Graphia** provides an interface offering a
wide range of options to **transform** **graphs** based on the
attributes of nodes and edges or the graph as a whole.

The **Transform List** is positioned at the top right of the graph
display window. When selected the **Add Transform** dialog box will
appear.

The available **graph transforms** are subdivided into categories:

  - **Analyses** has transforms that create new attributes using
    particular algorithms. These attributes can subsequently be
    visualised or used as a basis for further transformation.
  - **Attributes** has transforms that take existing attribute values
    and create new ones. The results of these transforms are often most
    useful for the purposes of visualisation.
  - **Filters** allow elements of the graph to be removed or retained
    based a supplied condition.
  - **Transforms** describes additional processes which do not neatly
    fit into the other categories.

**For a detailed description of individual transforms please go to the
[Transforms](Graphia:Transforms "wikilink") page.**

Upon selecting a transform, a short description is provided that
summarises the process involved. The remainder of the dialog is filled
with options pertaining to the transform in question. In the case of a
filter, a condition is required, whereas for other transforms, various
other settings are displayed.![Transform_list.png](Transform_list.png
"Transform_list.png")

After clicking **OK** the transform is calculated and applied to the
graph. Where this results in a change in the number of nodes or edges
the graph will automatically adjust to show the new topology.

**Active transformations** will be show in the top right hand corner of
the graph display window above the **Add Transform** button (bottom
figure).

Transforms are shown in the order they are carried out (top-to-bottom)
and may be dynamically adjusted by use of a slider or dialog box. The
order in which transforms are applied may be changed by holding down
left mouse button over **hamburger icon** and moving transform up or
down.

The arrow next to the **Add Transform** button hides the transform list.

![Visualisation_Menu.png](Visualisation_Menu.png
"Visualisation_Menu.png")

### Visualisation Options

**Graphia** has a range of options to superimpose information on the
graph based on attributes of nodes and edges. The **Add Visualisation**
button is positioned at the bottom right of the graph display window.
When selected the **Add Visualisation** dialog box will appear.

Select an **Attribute** then decide whether you wish it to be displayed
as **text**, **size** or **colour**. Then press **OK**. In the case of
figure shown on the right, user has chosen to select the edge attribute
'Pearson correlation' and to 'Colour' edges according to edge weight.
Details of the visualisation will be shown on the the bottom right of
the graph display, below the Add Visualisation button.

Once applied to a graph a visualisation can be changed. To change the:

  - **Attribute** being displayed click the attribute name and select
    another from the list.
  - **Colour Scheme** click on the key to select or change its style.
      - **Gradient** click the hamburger icon to invert how the colours
        are applied.
      - **Palette** click the hamburger icon to select whether colours
        are assigned alphabetically, by value or by quantity - how
        frequently the values occur.

Multiple visualisation schemes may be selected at once but later schemes
will override earlier visualisations when they compete.

The arrow next to the **Add Visualisation** button hides the
visualisation list.

### Cluster Analysis

![Cluster_window.png](Cluster_window.png "Cluster_window.png") The aim
of a cluster analysis is to group a set of objects, in the context of a
graph - nodes, in such a way that nodes in one **cluster** are more
similar to each other than to those in other **clusters**. Once
clustered a graph can be viewed as a set **node clusters.** In the
context of a correlation graph, clustering can be used as a means to
**discover** and **explore patterns** in the source data.

**Graphia** uses the **[MCL](https://micans.org/mcl/) algorithm**, a
fast and tunable approach to graph clustering. It determines clusters
based purely on their connectivity.

To perform a cluster analysis, left click **Add Transform** on the top
right of the graph window, and when dialog appears select **MCL
Cluster** on the left and then click **OK**. Clusters will be shown on
the graph, the largest cluster being **Cluster 1**, subsequent clusters
being of decreasing size, and nodes belonging to the same cluster
possessing the same colour. The colour assignments of the largest
clusters will appear on the bottom right of the screen and can be
changed by clicking on the key.

The **granularity** setting of clustering can be adjusted using the
slider provided, or a value entered directly.

Once clustered a dataset can be rapidly explored, scrolling through the
clusters using the attribute viewer (Ctrl+H) to examine the data
patterns therein and clusters can also be explored for their
**enrichment** of nodes with particular attributes (below).
![Enrichment_analysis_results_window.png](Enrichment_analysis_results_window.png
"Enrichment_analysis_results_window.png")

### Enrichment Analysis

Although it is not strictly speaking a network analysis tool,
**enrichment analysis** is often used in combination with topological
network analysis.

There are different varieties of this type of analysis, but in its most
basic form, enrichment analysis is used to infer **which annotations are
over-represented** in a selection of network. **Graphia** uses a type of
a hypergeometric ([Fisher's
exact](wikipedia:Fisher's_exact_test "wikilink")) test to answer the
following question:

*"When sampling* *X* *nodes (test set) out of* *N* *nodes (input data),
what is the probability that* *x* *or more of these nodes have an
attribute* *C, that is* *shared by* *n* *of the* *N* *nodes in the
reference set."*

In other words, given the frequency of a given attribute in the dataset,
what the chance of finding so many nodes in a selection (cluster) with
that attribute. It helps explain what a cluster may represent based on
prior knowledge.

To perform an enrichment analysis, select **Analyses -\> Enrichment**
from the menu. When presented with the first dialog select the first
attribute class (**A**) and in the second window the second attribute
class (**B**). The tool will then calculate whether values for attribute
**B** are enriched in nodes in with attribute **A** and display the
results.

The results table of enrichment scores. On the left are the **tabulated
values for enrichment** (\<0.05) showing the observed vs. expected and
results of Fisher's exact test of those terms over-represented. On the
right is a **heatmap** of the results given in the table; clicking on
one of the areas in the heatmap will **highlight the corresponding data
in the table**.

**Icons above the table** offer options to also **show under represented
values**, **show/hide heatmap**, **delete results** and **perform
another analysis**.

### Attribute Table and Data Plot Viewer

![Attribute_table.png](Attribute_table.png "Attribute_table.png") The
**attribute viewer** is where attribute data relevant to the current
node selection is displayed. It is docked beneath the main graph display
by default, but it can also be detached and shown in a separate window
if desired.

**Node Attribute Table:** The node attribute table window provides
details of all selected nodes; their names and all associated attribute
information, both imported attributes and those that are calculated or
created by transforms. When nodes are first selected, all rows in the
table are also selected. Clicking on a single row will highlight that
associated node in the graph without deselecting others. Use the **Arrow
keys** to scroll the selection **up** or **down**. To select **multiple
consecutive rows** hold down **Shift+click** or **Ctrl+click** to select
individual rows.

The attribute has a toolbar with icons for common tasks. Their functions
may be determined by hovering the mouse and observing the tooltip
displayed. ![Attribute_viewer2.png](Attribute_viewer2.png
"Attribute_viewer2.png")

**Data Plot**: When doing a **correlation analysis**, the raw data for
selected nodes is also plotted. This allows a user to compare the
pattern of data associated with a node selection. It has been design to
produce publication ready plots.

The **Plot** menu provides options to alter the plot display. In
particular:

  - **Select Visible Column Attributes** sometimes correlation datasets
    have information associated with columns of data. These are referred
    to as **Column Attributes**. Clicking this option allows the user to
    choose which of these to display. Once selected, click the icon in
    the top left of the plot to confirm.

![IQR_plot.png](IQR_plot.png "IQR_plot.png")

  - **Scaling** display data rescaled by the specified means.
  - **Averaging** instead of showing individual lines for each node,
    show an average of the selection, using the specified means.
  - **Dispersion** show standard measures of dispersion.
  - **Include 0 in Y-axis** by default the Y-axis of the plot is chosen
    to maximise the available range based on the data. Selecting this
    option forces zero to be included in the plot.
  - **Sort By** the order in which to sort of the columns.

### Bookmarks

After inspecting the graph, you may wish to keep a record of node
selections that are interesting. Under the Bookmarks menu select **Add
Bookmark...** (Ctrl+D). After naming the bookmarked selection, you'll be
able to be able to easily return to that set of nodes at a later time.

### Selection

Related nodes may be selected using various options in the **Edit**
menu. In particular:

  - **Select Sources of Selection** refers to all the nodes whose
    outgoing edges point to the current selection
  - **Select Targets of Selection** refers to all the nodes whose
    incoming edges originate from the current selection
  - **Select Neighbours of Selection** refers to all the nodes that are
    directly connected to the current selection

These selection options can also be found in the context menu that is
shown by right clicking a node.

### Web search

Right clicking a node will show the context menu, including the option
to **Search \[the\] Web** for that nodes name. The default search engine
is Google but this can be changed under the **Options Dialog** (Misc
tab) such that graphs can be linked to a specific online resource.

### Export and saving data

During an analysis you may wish to save **screenshots** of the graph,
**export lists** of nodes and associated attribute data, **data plots**
or **analysis results**.

  - **Screenshots**: *File -\> Save Image As...*
  - **Export Table**: *Table -\> Export...*
  - **Data Plots**: *Plot -\> Save Image as...*
  -
Once an analysis is complete you can save the resulting graph in a
number of formats either by clicking the **save icon** on the top left
of the graph display window or ***File -\> Save.***

It is also possible to export the graph into the following common graph
formats. Note that some information may be lost in this process.

  - **GraphML**
  - **GML**
  - **Pairwise text**
  - **JSON Graph**
  -
## Troubleshooting

|                                                                |                                                                                                                                             |                                                                                                                                                                                                                                                             |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Problem**                                                    | **Possible reason**                                                                                                                         | **Possible solution**                                                                                                                                                                                                                                       |
| Authentication fails                                           | It is possible that your firewall is preventing the software communicating with Kajeka's servers.                                           | Try disabling any personal firewalls you may have installed. Failing that, please contact you local IT support.                                                                                                                                             |
| File will not load                                             | The input file is incorrectly formatted or corrupted.                                                                                       | [Check the input formats page.](Graphia:Input_formats "wikilink") Check the file for missing data, data outside the normal bounds, bad formatting, etc.. Also check the file extension as some programs e.g. Excel may add the wrong extension when saving. |
| Rendering of graphs is slow and jerky                          | The graph you are trying to display is larger than your system is able to display effectively, or your graphics drivers may be out of date. | Run smaller graphs, limit the graph size with a transform or upgrade system hardware. Install the latest graphics drivers available for your machine configuration.                                                                                         |
| I tried to load a file and Graphia has stopped responding      | Some tasks or files may use large quantities of compute resource.                                                                           | Take heed of any warnings suggesting that the resultant graph may be excessively large. Try adjusting parameters in order to generate a smaller graph, or use a computer with more memory.                                                                  |
| I experience image quality problems and/or text is oddly sized | Your graphics drivers may be out of date.                                                                                                   | Install the latest graphics drivers available for your machine configuration.                                                                                                                                                                               |

If you are still experiencing problems please email:
**<support@kajeka.com>**