---
title: Correlation Analysis Steps
---

From here on you may require many of Graphia’s visualisation and analytical capabilities described in Section 3.  In particular you may wish to:
- Adjust the correlation threshold. Displayed at top right hand corner of the screen, is a slider bar and text box for adjusting the display threshold between the initial threshold and 1.
- Cluster the graph. For correlation graphs we recommend use of the MCL algorithm.
- Display the data values associated with clusters – see below.

![]({{ site.url }}/guide/assets/s4-8.png)
Graphia’s user interface displaying a large correlation graph. The red nodes in the middle of the graph have been selected, the windows below showing their name and attributes, and to right, a plot of the data associated with them.

### Correlation graph – First view

All relationships with a value above the minimum threshold will be stored in memory, however only those edges with a value above the defined initial threshold will be displayed. This will be reflected in the Transform list.

![]({{ site.url }}/guide/assets/s4-9.png)
The transforms list immediately following correlation graph creation.

In the top right of the graph display window, there will be two transforms automatically added to the Transforms list.  The first, “Remove Edges where Pearson Correlation Value < [Initial Threshold]” will hide all edges with a correlation score below the value set. This value can be adjusted here and the effects will immediately apply to the graph. A large value will remove all but the highly correlated relationships while a low value will display the weaker relationships. The second “Remove Components where Component Size <= 1” will remove singular nodes from the display that have no connections.

![]({{ site.url }}/guide/assets/s4-10.png)
Effect of adjusting the correlation threshold on graph structure. As the r-threshold value is increased edges are lost and a graph opens up and potentially fragments. Sample-sample correlation matrix of transcriptomics experiment, node colours reflect time points after stimulation of mouse macrophages, although individual nodes may represent different experiment conditions, edges are coloured according to their weight (r-value) (data from: Raza et al., J. Leukocyte Biol. 96:167-83 (2014).

By adjusting the cut-off value for edges, you can ‘open up’ the graph to reveal underlying structure – what connects, and where are nodes relative to others.  Another option to help reveal the structure of a highly connected graph, is to apply an edge reduction method such as k-NN. Below shows the above graph before and after the k-NN edge reduction algorithm has been applied.

![]({{ site.url }}/guide/assets/s4-11.png)
Effect of running k-NN algorithm on sample-sample graph. When k-NN applied, here keeping only the top 5 correlated edges for each node, the structure opens up. On middle and right-hand graph node colours reflect time points after stimulation of mouse macrophages or experiment condition, respectively (data from: Raza et al., J. Leukocyte Biol. 96:167-83 (2014).

### Data plot window

This window is specific to graphs generated from numerical data and displays the data values associated with selected node(s). There are numerous options to change the appearance of this plot window, these will be discussed below.

### Cluster analysis

Once a correlation graph has been generated, a common first step is to run a clustering algorithm on the graph. This partitions the graph into clusters based on the connectivity between nodes, with the result that entities with a similar data profile are located with the same cluster.  For correlation graphs where the average node degree is high, we recommend the use of the MCL algorithm. The granularity setting for clustering can be adjusted on fly by use of the slider bar, such that the clustering reflects the visible graph structure. Once satisfied with the partition of a graph, a user can then rapidly explore the profile of the resulting clusters. 

Go to Edit menu -> Find by Attribute Value (Ctrl+H) and the following menu will appear in the top left of the graph display window, and the first attribute in the class (in this case MCL cluster) will be displayed. Clicking arrows will scroll through attributes in that class. By clicking on the attribute type you can select other attributes to visualise upon the graph.

![]({{ site.url }}/guide/assets/s4-12.png)
Gene correlation graph, following clustering. A single cluster (cluster 1) has been selected and its identity and properties (user defined and calculated) are shown below in the attribute table window to the left and its expression profile is plotted in the graph display window to the right. Each line represents the data associated with a single node.

Having clustered a graph the next thing is to view the profile of those clusters and there are numerous options available to do this.

![]({{ site.url }}/guide/assets/s4-13.png)
Options for viewing cluster profile. (A) A single cluster with the profile of individual nodes on display.  Mouse over a given data point with provide details. Note column attributes have been displayed under the line graph using the ‘Select Visible Column Annotations’ button and selecting those of interest. This allows easy alignment between know variables and the data; (B) Mean histogram of A; (C) IQR plot of A; (D) Mean line of two clusters (1,2) showing anti-correlation; (E) Combined plot of all clusters; (F) Various menu options accessed by right click on data plot window.

Graphia is designed to let a user quickly explore data clusters, defining what is interesting, what is ‘noise’ and what data patterns are due to technical or other reasons. Having selected a specific cluster, individual data points within that cluster may be selected in the attribute display window. By scrolling up and down with the arrow keys, different entities within a list may be explored.   After an initial analysis it may be necessary to look again at the input data, possibly recalculating values or removing data that is not of interest, therefore focusing an analysis on what is interesting. Beyond this there are many other ways that one might wish to explore or change the settings for graph visualisation as outlined in section 3.

_Graphia is designed only to allow you, a user, to explore, analyse and interrogate data, how you do this and what you do with the insights obtained, is up to you._
