---
title: Graph-related terms and concepts
---

## Graph layout
Graph layout is the process of placing nodes and edges for the purposes of visualising data structure, in other words, ordering of the information for visual inspection

Graphs may be drawn manually, placing nodes and edges in specific positions. Inthe case of the London Underground map for example, node positions do not represent the actual geographical position of a station, but rather are approximations, stations being placed in a way designed to make the map easierto read and interpret.

For most networks however, graph layout is achieved by means of a layout algorithm that places nodes and edges according to sets of rules.  There are numerous different types of layout algorithm, but perhaps the most commonly used kind are called force-directed layout algorithms. The approach relies on generating repulsive forces between all graph nodes and attractive forces between adjacent nodes, positioning them so these forces reach a minimal state.

It should be noted that the layout of a graph does not affect its properties, i.e. nodes still have the same number of edges and they connect in the same way, only how the information is displayed is different.

## Node degree

Simply put, node degree is the number of edges a node has. In directed graphs,you may talk about a node’s ‘in degree’ or ‘out degree’, referring to the edges that point at it or away from it, respectively. The number and distribution of edges across a graph determines its topology.

## Topology 

A graph’s topology or structure is dependent on the source of data it representsand how nodes are connected. Ultimately, this affects the appearance of the graph or its ‘shape’. Nodes with many edges may represent hubs and big graphs may look like ‘hairballs’ or be highly structured entities with numerous areas of high connectivity leading to cliques within the graph structure. You can tell a lot about given a set of data by the topology of the graph it forms

## Components

A component is a portion of a graph where a number of nodes are connected to each other but are unconnected to other parts of the graph.  In other words, the data provided separates into unconnected groupings.

## Attributes

Each node or edge may be associated with additional information, called attribute data or metadata. For example, if a node represents a person, we might also know information on that individual’s, age, gender, ethnicity, height, weight, diet, etc.  In the case of edges, it may be that there are different values associated with them, e.g. correlation values, or they may represent a different source or kind of information that connects two entities.

## Clustering

Perhaps the most useful approach to understanding the structure of a large graph is to perform a cluster analysis.Clustering is the act of dividing a graph upinto groups of nodes, clusters, based on their relative position within the overall topology of the graph. The assumption being that areas of a graph represent communities where nodes possess similar properties or characteristics. There area numerous algorithms available to analyse graphs in this way, and whilst using even a single clustering algorithm, the option to change the granularity of clustering, i.e. how many clusters are formed, is often available.  There is no simple answer to the question of what the correct clustering of a graph is, but good visualisation allows one to look at the results of a cluster analysis and how it maps on to a graph’s structure.

![]({{ site.url }}/guide/assets/s1-5.png)
A representation of a clustering 


