---
title: What Type of Data Can I Analyse with Graphia?
---


## Network data
Graphia can be used to analyse a wide variety of data types from almost any source, as long as it can be abstracted into a graph, i.e. the relationship betweenentities are known in advance. If you also have additional metadata, i.e. additional information on the nodes and edges, this can be imported and explored as node/edge attributes. This information may be stored in a database or spreadsheet but will need to be in the right format for loading and analysis within Graphia.

Simple lists of nodes and edges may be loaded as two columns, the implication isthat there is a relationship between the node defined in column 1 and the node in column 2, and loaded as a text file (.txt). Such information can also be encoded as an adjacency matrix and loaded as a comma/tab separated variable file (.csv, .tsv)

More complex definitions of a graph, including information such as the colour or shape of nodes, their position, associated metadata, etc., may be encoded using a number of standard graph-based file formats, e.g. GraphML (.graphml), Graph Modelling (.gml) JSON Graph (.json), MATLAB data files [array] (.mat). These are widely used standard file formats and are frequently supported for data export formats in other graph analysis packages.

For more information on working with network data, see Section 3.

## Numerical Data
This is where correlation analysis comes in. Correlation analysis works to define how similar one entity is to another based on any numerical data series associated with them. By only using the strongest relationships between entities to define edges, you can rapidly identify groups of entities that behave similarly. In other words, you can identify patterns and trends within the data.

Correlation analysis can be used as basis to explore any spreadsheet of numbers relating to any set of entities, whether they are discrete, (0, 1) or continuous values. One of Graphia’s USPs is its ability, where necessary, to calculate and render massive correlation graphs from big datasets.

Graphia supports the following file formats for performing correlation analysis, a spreadsheet of values and where appropriate, attribute information (.csv, .tsv, .xlsx)

For more information on working with network data, see Section 4.