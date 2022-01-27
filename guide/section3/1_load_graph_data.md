---
title: Loading Graph Data
next: 2_transforms_visualisation_analyses
---

## Loading Graph Data
For an analysis to proceed, data needs to be presented to Graphia in one of the supported file formats. Graphia will allow you to load any data in the right format, and it will quickly highlight any errors or issues with the data's format. Once explored, it is not uncommon that data will need to be refined and then reloaded. Graphia supports a wide range of data types derived from many sources, in this section we will deal with data that is already in a graph format and the tools available for its exploration and analysis.
For small datasets without attributes, pairwise (.txt) is a very simple and easy to construct format. Adjacency matrices can be loaded as (.csv, .tsv). For most other datasets, we recommend using a standardised graph format such as GML.

Graphia supports the following file formats:
- Adjacency Matrix (.csv, .tsv, .xlsx)
- Biopax OWL (.owl)
- Cytoscape Exchange (.cx, .cx2)
- Graphviz DOT (.dot)
- GraphML (.graphml)
- Graph Modelling Language (.gml)
- JSON Graph (.json)
- MATLAB data files (.mat)
- Pairwise (.txt, .csv, .tsv, .xlsx)

These files can be loaded directly into Graphia navigating to *File → Open* or by clicking the open icon in the top left of the toolbar.

{% include guide-nav.html %}
