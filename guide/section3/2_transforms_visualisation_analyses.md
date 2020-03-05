## Graph Transforms

Graph transformation is central concept of Graphia. Transforms are a range of processes by which a graph is modified to produce a new graph or calculate a new attribute. Graphia incorporates a wide range of options that allow an analyst to perform a sophisticated range of data transformations and analyses. These include processes such as graph clustering, edge reduction, node/edge filtering based on attributes, calculation of graph metrics or algorithms that change the structure of a graph. Graphia’s interface for performing graph transforms has been designed to be powerful and flexible, the results immediately modifying a graph’s structure or appearance.

The “Add Transform” button can be found in the top-right of the graph view. From here a list of transforms can be added to the graph. For a more detailed look view our transforms page

Graphia has a sophisticated and flexible transform interface for modifying graphs on-the-fly. Active transforms are displayed in a Transform List in the top-right of the Graph view. Transforms are applied top-down; the transform at the top of the list will apply first, the results are then fed into the second transform and so on down the list. The final graph will be displayed in the view.

![]({{ site.url }}/guide/assets/s3-2.png)
Transform list showing three active transforms, shown in the order in which they are applied, top to bottom (left). Right click on three bar icon to display options for modifying a transform (right). New transforms can be added at any time by left clicking the Add Transform button and the order in which transforms are applied by left clicking three bar icon and moving the position of the icon. Transforms can be pinned to the bottom of the list to prevent new transforms from moving.

Clicking “Add Transform” will bring up the Add Transform dialog.

![]({{ site.url }}/guide/assets/s3-3.png)
The cluster dialog providing the means to select clustering algorithm and granularity setting.

From here you are presented with a list of all transforms available, separated by category. Clicking on a transform from the list will display a list of options as well as a brief description of the transform.

- Attributes provides a means to modify or add new attributes based on existing attributes in the graph.
- Clustering provides options for clustering a graph.
- Edge reduction provides a means to globally reduce the number of edges in a graph. 
- Filters provides options to remove or keep elements based on their attributes.
- Metrics includes a number of algorithms to analyse the positional characteristics of elements in a graph.
- Structural includes a range of algorithms that will change the structure of a graph, based on defined criteria.

Some transforms provide the option to automatically apply a visualisation after adding. Clicking OK will finalise the transform and add it to the Graph. We describe some of the most commonly used transforms below. 

### Clustering

Clustering is the act of dividing a graph up into groups of nodes, clusters, based on their position within the overall topology of the graph. Clustering seeks to divide the graph into communities where nodes likely possess similar properties or characteristics. Graphia incorporates two of the most widely used algorithms for performing this analysis, the Markov Clustering (MCL) and Louvain clustering algorithms.  Both include the option to change the granularity of clustering, i.e. how many clusters are formed.  There is no simple answer to the question of what the correct clustering of a graph is, but good visualisation allows one to look at the results of a cluster analysis and how it maps on to a graph’s structure. Once data has been clustered, clusters can be analysed by enrichment analysis to see if there are any node attributes over-represented within the groups.   

### Edge Reduction

In some graphs the number of edges can be exceptionally large. Not only can these be difficult to render they may add little to the overall structure and may actually obscure higher level groupings. The k-nearest neighbours (k-NN) algorithm is a widely used for globally reducing the number of edges in a graph, such a given node has a maximum number of edges. In a weighted edge graph this would generally those with the highest weights.  A modification of the principle is to retain only a given percent of the edges for any given node (%-NN) or to randomly reduce edges (Edge Reduction) as none have any more significance than others.

![]({{ site.url }}/guide/assets/s3-4.png)
The bcsstk31 (BCS Structural Engineering Matrices - Statics module of an automobile component) graph, with and without edge reduction. Note, the retention of graph structure even with <25% edges.

### Filters

The filters menu allows a user to remove nodes or edges based on their attributes calculated or user-defined. It provides a functionally rich menu with which to transform a graph based a wide range of criteria.

![]({{ site.url }}/guide/assets/s3-5.png)
The filter dialog. In this instance the selection reads: ‘Remove nodes where the node degree is less than 5.’

### Metrics
Graphia includes three metrics for analysing a graphs structure:
- Betweenness centrality is a measure of centrality in a graph based on the shortest paths between nodes. The betweeness centrality is the number of these shortest paths that pass through the node.
- Eccentricity calculates the shortest path between every node and assigns the longest path length found for each node. This is a measure of a node’s position within the overall graph structure. 
- PageRank is an algorithm used originally to measure the importance of website pages. PageRank works by counting the number and quality of links to a page to determine a rough estimate of how important a node is.

![]({{ site.url }}/guide/assets/s3-6.png)
Visual display of attribute data. (A) Display of clusters (categorical attribute); (B) following ‘Remove Leaves’ transformation; (C) visualisation of Betweeness centrality values; (D) Eccentricity values; (E) PageRank values; (F) Node degree values. C-D are continuous attributes, so colour spectrum and size used for display. Betweenness and eccentricity are calculated for both nodes and edges and therefore visual encoding is applied to both.

### Visualisation of Attribute Information

Visualisations are another important concept within Graphia. Associated with nodes and edges are various properties or attributes.  This information may have been loaded from the input file or calculated within the tool and displayed upon a graph. Visualisations are often tied to the output of Transforms; for example a clustering transform will automatically apply a colour visualisation, so each cluster is coloured differently.

Visualisations can be one of the following types:

- Colour – For text based attributes this will apply a unique colour to an element for each entry. Numerical values will be displayed as a colour range or gradient. Clicking on a colour visualisation will allow you to further customise the output
- Size – This will scale elements to match the range of attribute values (Numerical Only)
- Text – This will display the attribute value as text in the graph. The visibility of graph text can be changed via View -> Show Node/Edge Text. The font and size of text can be adjusted in the settings dialog.

Clicking “Add Visualisation” (bottom right of graph display window) will open the Add Visualisation dialog.

![]({{ site.url }}/guide/assets/s3-7.png)
Visualisation dialog. First select the node or edge attribute you wish to visualise and then how you wish to display this (colour, size, text)

Visualisations operate in a list, similarly to how Transforms work. Visualisations update to match the data within the graph.

![]({{ site.url }}/guide/assets/s3-8.png)
Visualisation list containing two visualisations. MCL Cluster attribute as a colour visualisation and Edge betweenness attribute as a size visualisation.

In the case of categorical attributes each attribute is assigned a colour, numerical attributes are displayed using a spectrum of colour. Clicking on the colour palette associated with a given visualisation will allow you to change the colour scheme of the whole palette or the colour assigned to individual attributes.

![]({{ site.url }}/guide/assets/s3-9.png)
A simple graph with colour, size and text visualisations applied to represent node degree (orthographic view).

Each visualisation operates within its domain and does not interfere with other visualisations of a different type, for example a colour visualisation will not interfere with a text visualisation. However two visualisations of the same type will overlap, with the last visualisation in the list taking precedence. Multiple visualisations of the same type can be in the same list without overlapping, assuming they apply to separate graph elements.