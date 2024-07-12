---
title: Saving Graphs, Analysis Results and Outputs
prev: 5_attributes
next: 7_enrichment
---

{% include guide-nav.html %}

## Saving
Having performed an analysis one needs save the results. Graphia allows you to export tables of results or publication quality images of the graphs and data plots, for subsequent communication of the results to others.

## Graphs
Graphia supports exporting graphs in a variety of different formats. Exported files will include all node and edge attribute values. (Excluding pairwise, since it does not support additional meta-data and will only preserve the node name and graph topology.)

To export a graph, go to *File → Save As…* and select the file format from the dropdown.
- GraphML
- GML
- JSON (JSON Graph)
- Pairwise (.txt)

## Table Data
Tabular data can also be exported from the attribute viewer and the enrichment results by right clicking the tables and clicking *Export…*. Data will be exported as either .csv or .tsv. These formats can be opened using a spreadsheet application.

## Outputs
Graphia also has an image capture feature available from *File → Save As Image…* allowing you to capture a range of high resolution and publication ready images. To quickly share a normal resolution screenshot, Ctrl+C can be used to copy the current graph display to the clipboard.

{% include guide-nav.html %}
