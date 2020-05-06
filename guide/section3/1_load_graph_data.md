---
title: Loading Graph Data
---

## Loading Graph Data
For an analysis to proceed, data needs to be presented to Graphia in one of the supported file formats. Graphia will allow you to load any data in the right format, and it will quickly highlight any errors or issues with the data's format. Once explored, it is not uncommon that data will need to be refined and then reloaded. Graphia supports a wide range of data types derived from many sources, in this section we will deal with data that is already in a graph format and the tools available for its exploration and analysis.
If your data already has an obvious node and edge structure, i.e. the relationships are already defined, we recommend loading it via a graph-based file format. For small datasets without attributes, pairwise (.txt) is a very simple and easy to construct format. If formatted as an adjacency matrix these can be loaded as (.csv, .tsv). For most other datasets, we recommend using one of the standard graph formats such as GML.

Graphia supports the following file formats:
- Pairwise (.txt)
- JSON Graph (.json)
- GraphML (.graphml)
- Graph Modelling Language (.gml)
- Adjacency Matrix (.csv, .tsv)
- MATLAB data files (.mat)

These files can be loaded directly into Graphia navigating to File → Open or by clicking the open icon in the top left of the toolbar.
