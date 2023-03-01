---
title: Loading Graph Data
next: 2_transforms
---

## Loading Graph Data
For an analysis to proceed, data needs to be presented to Graphia in one of the supported file formats. Graphia will allow you to load any data in the right format, and it will quickly highlight any errors or issues with the data's format. Once explored, it is not uncommon that data will need to be refined and then reloaded. Graphia supports a wide range of data types derived from many sources, in this section we will deal with data that is already in a graph format and the tools available for its exploration and analysis.
For small datasets without attributes, pairwise (.txt) is a very simple and easy to construct format. Adjacency matrices can be loaded as (.csv, .tsv). For most other datasets, we recommend using a standardised graph format such as GML.

Graphia supports the following file formats:
- Adjacency Matrix (.csv, .tsv, .xlsx)
- [Biopax OWL](http://www.biopax.org/owldoc/Level3/) (.owl)
- [Cytoscape Exchange](https://home.ndexbio.org/data-model/) (.cx, .cx2)
- [Graphviz DOT](https://www.graphviz.org/doc/info/lang.html) (.dot)
- [GraphML](http://graphml.graphdrawing.org/primer/graphml-primer.html) (.graphml)
- [Graph Modelling Language](https://github.com/GunterMueller/UNI_PASSAU_FMI_Graph_Drawing/blob/master/GML/gml-technical-report.pdf) (.gml)
- [JSON Graph](https://jsongraphformat.info/) (.json)
- MATLAB data files (.mat)
- Pairwise (.txt, .csv, .tsv, .xlsx)

These files can be loaded directly into Graphia navigating to *File → Open* or by clicking the open icon in the top left of the toolbar.

In particular, when dealing with pairwise data, the following dialog will be displayed. In this case the meaning of each column can be selected, enabling flexible workflows where the format of the input data is not necessarily fixed.

![]({{ site.url }}/guide/assets/pairwise-parameters.png)
<div class="caption">The Pairwise Parameters dialog.</div>

{% include guide-nav.html %}
