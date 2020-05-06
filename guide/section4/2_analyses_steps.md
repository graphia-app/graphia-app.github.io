---
title: Correlation Analysis Steps
---

## Correlation Analysis

From here on you may require many of Graphia's visualisation and analytical capabilities described in the previous section. In particular you may wish to:
- Adjust the correlation threshold. Displayed at top right hand corner of the screen is a slider bar and text box for adjusting the display threshold between the minimum threshold and 1.
- Cluster the graph. For correlation graphs we recommend use of the MCL algorithm.
- Display the data values associated with clusters - see below.

![]({{ site.baseurl }}/guide/assets/s4-8.png)
_A correlation graph. The nodes in the middle of the graph have been selected, and the table below shows their names and attributes. Similarly, the plot shows the data associated with the selection._

## Correlation Graph - First view

Edges are created for any relationships with a correlation value above the minimum threshold, however only those edges with a value above the defined initial threshold will be displayed. This value is adjustable in the transform list.

![]({{ site.baseurl }}/guide/assets/s4-9.png)
_The transforms list immediately following correlation graph creation._

There are two transforms automatically added to the transforms list. The first, **Remove Edges where Pearson Correlation Value < [Initial Threshold]**, will remove all edges with a correlation score below the value set. This value can be adjusted here and its effects will be immediately applied to the graph. A large value will remove all but the most highly correlated relationships while a low value will display the weaker relationships. The second, **Remove Components where Component Size ≤ 1**, will remove singular nodes from the display that have no connections.

![]({{ site.baseurl }}/guide/assets/s4-10.png)
_The effect of adjusting the correlation threshold on graph structure. As the r-threshold value is increased edges are lost and a graph spreads out, then potentially fragments. Sample-sample correlation matrix of transcriptomics experiment, node colours reflect time points after stimulation of mouse macrophages, although individual nodes may represent different experiment conditions, edges are coloured according to their weight (r-value) (data from: Raza et al., J. Leukocyte Biol. 96:167-83 (2014)._

By adjusting the cut-off value for edges, you can 'open up' the graph to reveal underlying structure - what connects, and where the nodes are relative to others. Another option to help reveal the structure of a highly connected graph is to apply an edge reduction method such as k-NN. Below shows the above graph before and after the k-NN edge reduction algorithm has been applied.

![]({{ site.baseurl }}/guide/assets/s4-11.png)
_The effect of running k-NN algorithm on sample-sample graph. When k-NN applied the structure opens up, in this case keeping only the top 5 correlated edges for each node. On the middle and right-hand graph, node colours reflect time points after stimulation of mouse macrophages or experiment condition, respectively (data from: Raza et al., J. Leukocyte Biol. 96:167-83 (2014)._

## Data Plot

When performing a correlation analysis, a data plot is also displayed adjacent to the usual attribute table. This plot displays the data values associated with selected nodes. There are numerous options to change the appearance of this plot, these will be discussed below.

## Cluster Analysis

Once a correlation graph has been generated, a common first step is to run a clustering algorithm. This partitions the graph into clusters based on the connectivity between nodes, with the result that entities with a similar data profile are located within the same cluster. For correlation graphs where the average node degree is high, we recommend the use of the MCL algorithm. The granularity setting for clustering can be adjusted on fly by use of the slider bar, such that the clustering reflects the visible graph structure. Once satisfied with the partition of a graph, a user can then rapidly explore the profile of the resulting clusters. 

Go to Edit → Find by Attribute Value and the following user interface will appear in the top left of the window. This allows finding all the nodes which have a particular value for the selected attribute. In the context of clustering, this allows the user to scroll through the calculated clusters. Selecting the option to the right of the attribute selector allows finding of multiple clusters at once.

![]({{ site.baseurl }}/guide/assets/s4-12.png)
_Gene correlation graph, following clustering. A single cluster (cluster 1) has been selected and its identity and properties are shown below in the attribute table window and its expression profile is plotted to the right. Each line represents the data associated with a single node._

Having clustered a graph the next thing is to view the profile of those clusters and there are numerous options available to do this:

![]({{ site.baseurl }}/guide/assets/s4-13.png)
_Options for viewing cluster profile. (A) A single cluster with the profile of individual nodes on display. Hovering over a given data point will provide details. Note column annotations have been displayed under the line graph using the 'Select Visible Column Annotations' button and selecting those of interest. This allows easy alignment between known variables and the data; (B) Mean histogram of A; (C) IQR plot of A; (D) Mean line of two clusters (1,2) showing anti-correlation; (E) Combined plot of all clusters; (F) Various menu options accessed by right click on data plot window._

Graphia is designed to let a user quickly explore data clusters, defining what is interesting and what is 'noise'. Having selected a specific cluster, individual data points within that cluster may be selected in the attribute table. By scrolling up and down with the arrow keys, individual nodes within the selection are highlighted, and their data profiles displayed in the plot. After an initial analysis it may be necessary to look again at the input data, possibly recalculating values or removing data that is not of interest, therefore focusing an analysis on what is interesting.

_Graphia is designed to allow you to explore, analyse and interrogate data, it is up to you how you do this and what you do with the insights obtained._
