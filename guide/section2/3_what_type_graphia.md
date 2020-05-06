---
title: What Type of Data Can I Analyse with Graphia?
---

## Graph Data
Graphia can be used to analyse a wide variety of data types from almost any source, as long as it can be abstracted into a graph, i.e. the relationships between entities are known in advance. If you also have additional metadata, i.e. information relating to individual nodes and edges, this can be imported and explored as node/edge attributes. This information may be stored in a database or spreadsheet but will need to be in the right format for loading and analysis.

Simple lists of nodes and edges may be loaded as two columns, the implication is that there is a relationship between the node defined in column 1 and the node in column 2, and loaded as a text file (.txt). Such information can also be encoded as an adjacency matrix or loaded from a comma/tab separated variable file (.csv, .tsv)

More complex definitions of a graph may be encoded using a number of standard graph based file formats, for example GraphML, GML, JSON Graph, or MATLAB data files. These are widely used standard file formats and are frequently available for as export formats from other graph analysis packages.

For more information on working with graph data, see the Graph Analysis section.

## Numerical Data
This is where correlation analysis comes in. Correlation analysis works to define how similar one entity is to another based on any numerical data series associated with them. By only using the strongest relationships between entities to define edges, you can rapidly identify groups of entities that behave similarly. In other words, you can identify patterns and trends within the data.

Correlation analysis can be used as basis to explore any table of numbers relating to any set of entities, whether they are discrete or continuous values. One of Graphia's unique selling points is its ability to calculate and render massive correlation graphs from big datasets.

For more information on working with numerical data, see the Correlation Network Analysis section.
