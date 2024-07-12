---
title: Correlation Analysis Steps
prev: 1_loading_numerical
---

## Correlation Analysis

From here on you may require many of Graphia's visualisation and analytical capabilities described in the previous section. In particular you may wish to:
- Adjust the correlation threshold. Displayed at top right hand corner of the screen is a slider bar and text box for adjusting the display threshold between the minimum threshold and 1.
- Cluster the graph, if a clustering transform was not selected in the wizard.
- Display the data values associated with clusters - see below.

![]({{ site.url }}/guide/assets/correlation-clusters.png)
<div class="caption">A correlation graph. The nodes in the middle of the graph have been selected, and the table below shows their names and attributes. Similarly, the plot shows the data associated with the selection.</div>

## Correlation Graph - First view

Edges are created for any relationships with a correlation value above the minimum threshold, however only those edges with a value above the defined initial threshold will be displayed. This value is adjustable in the transform list.

![]({{ site.url }}/guide/assets/correlation-transforms.png)
<div class="caption">The transforms list immediately following correlation graph creation.</div>

There are two transforms automatically added to the transforms list. The first, **Remove Edges where Pearson Correlation Value < [Initial Threshold]**, will remove all edges with a correlation score below the value set. This value can be adjusted here and its effects will be immediately applied to the graph. A large value will remove all but the most highly correlated relationships while a low value will display the weaker relationships. The second, **Remove Components where Component Size ≤ 1**, will remove singular nodes from the display that have no connections.

![]({{ site.url }}/guide/assets/correlation-threshold.png)
<div class="caption">The effect of adjusting the correlation threshold on graph structure. As the r-threshold value is increased edges are lost and a graph spreads out, then potentially fragments. Sample-sample correlation matrix of transcriptomics experiment, node colours reflect time points after stimulation of mouse macrophages, although individual nodes may represent different experiment conditions, edges are coloured according to their weight (r-value) (data from: Raza et al., J. Leukocyte Biol. 96:167-83 (2014).</div>

By adjusting the cut-off value for edges, you can 'open up' the graph to reveal underlying structure - what connects, and where the nodes are relative to others. Another option to help reveal the structure of a highly connected graph is to apply an edge reduction method such as k-NN. Below shows the above graph before and after the k-NN edge reduction algorithm has been applied.

![]({{ site.url }}/guide/assets/correlation-knn.png)
<div class="caption">The effect of running k-NN algorithm on sample-sample graph. When k-NN applied the structure opens up, in this case keeping only the top 5 correlated edges for each node. On the middle and right-hand graph, node colours reflect time points after stimulation of mouse macrophages or experiment condition, respectively (data from: Raza et al., J. Leukocyte Biol. 96:167-83 (2014).</div>

## Data Plot

When performing a correlation analysis, a data plot is also displayed adjacent to the usual attribute table. This plot displays the data values associated with selected nodes. There are numerous options to change the appearance of this plot, these are discussed below.

## Cluster Analysis

Once a correlation graph has been generated, a common first step is to run a clustering algorithm. This partitions the graph into clusters based on the connectivity between nodes, with the result that entities with a similar data profile are located within the same cluster. For correlation graphs where the average node degree is high, we recommend the use of the MCL algorithm. The granularity setting for clustering can be adjusted on fly by use of the slider bar, such that the clustering reflects the visible graph structure. Once satisfied with the partition of a graph, a user can then rapidly explore the profile of the resulting clusters.

Go to *Edit → Find by Attribute Value* and the following user interface will appear in the top left of the window. This allows finding all the nodes which have a particular value for the selected attribute. In the context of clustering, this allows the user to scroll through the calculated clusters. Multiple clusters can be selected at once using the option immediately to the right of the attribute selector; *Select Multiple*.

![]({{ site.url }}/guide/assets/correlation-fbav.png)
<div class="caption">Gene correlation graph, following clustering. A single cluster (cluster 1) has been selected and its identity and properties are shown below in the attribute table window and its expression profile is plotted to the right. Each line represents the data associated with a single node.</div>

The data profile of the selected nodes is displayed in the lower right of the window. There are numerous options available to control this, examples of which are shown here:

![]({{ site.url }}/guide/assets/correlation-plot.png)
<div class="caption">Options for viewing cluster profile. (A) A single cluster with the profile of individual nodes on display. Hovering over a given data point will provide details. Note column annotations have been displayed under the line graph using the 'Select Visible Column Annotations' button and selecting those of interest. This allows easy alignment between known variables and the data; (B) Mean histogram of A; (C) IQR plot of A; (D) Mean line of two clusters (1,2) showing anti-correlation; (E) Combined plot of all clusters; (F) Various options accessed by the Plot menu.</div>

Graphia is designed to let a user quickly explore data clusters, defining what is interesting and what is 'noise'. Having selected a specific cluster, individual data points within that cluster may be selected in the attribute table. By scrolling up and down within the data table, individual nodes are highlighted, and their data profiles displayed in the plot. After an initial analysis it may be necessary to look again at the input data, possibly recalculating values or removing data that is not of interest, therefore focusing an analysis on what is interesting.

## Find Rows of Interest

When examining correlation data, sometimes it is helpful to be able to isolate the graph nodes that correspond to distinct columns in the source data set. This is the purpose of the *Find Rows of Interest* function. After enabling said function, one or more columns in the data plot must be selected. Thereafter, any node selection will have its corresponsing data row selection reduced such that only the top most rows are shown in the data plot. The number of highlighted rows can be changed by adjusting the *Percentile* slider. The nature of the selection is also mutable via the *Selection Weighting* slider. Broadly speaking, this allows for finding either rows that have peaks in the selected columns (denoted Absoute) or for finding rows that have significant values specifically in the selected columns (denoted Relative). Note that columns can also be selected via *Column Annotation*.

![]({{ site.url }}/guide/assets/find-rows-of-interest.png)

{% include guide-nav.html %}
