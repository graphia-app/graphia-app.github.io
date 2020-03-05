### Analyses

#### [Eccentricity](wikipedia:Distance_\(graph_theory\) "wikilink")

Calculates the shortest path between every node and assigns the longest
path length found for that node. This is a measure of a node's position
within the overall graph structure.

#### [MCL](https://micans.org/mcl/) Cluster

Finds discrete groups (clusters) of nodes based on a flow simulation
model.

<File:Before> MCL.png|Unclustered graph <File:After> MCL.png|Colours
represent clustered nodes

#### [PageRank](wikipedia:PageRank "wikilink")

[Centrality](wikipedia:Centrality "wikilink") measurement for each node.
This can be viewed as measure of a node's relative importance in the
graph.

### Attributes

#### Attribute Synthesis

In some situations an attribute may contain some useful information, in
amongst other data. The Attribute Synthesis transform allows a new
attribute to be created based on the values containing in an existing
one. Values are extracted from attributes by using [regular
expression](wikipedia:Regular_expression "wikilink") captures.

<File:Attribute> Synthesis Before.png|The original attribute contains a
lot of information, but for our purposes, we're only interested in the
part before the first comma... <File:Attribute> Synthesis
After.png|...so we can apply an Attribute Synthesis transform that
extracts this section, and creates a new attribute named Major Food

#### Boolean Attribute

Create an attribute whose value is the result of the specified
condition. The attribute is always given the value True or False. These
transforms are primarily useful for creating an attribute that can
subsequently be used for visualising conditional information. In the
following example, the yellow edges are those that have a correlation
coefficient above a given threshold, whereas the red nodes are those
whose names include a particular bit of text.

<File:Boolean> Attribute Before.png <File:Boolean> Attribute After.png

#### Combine Attributes

Create a new attribute by combining two other attributes.

<File:Combine> Attributes.png|Group (sub-class) and MCL Cluster have
been combined to create a third attribute named Group Cluster

### Filters

Remove nodes, edges or components based on a condition. These transforms
are the most fundamental way to transform a graph. Note that the filters
are expressed in two ways: Remove and Keep. These are functionally
equivalent, but with the sense of the conditional reversed. The reason
to present both is that sometimes it is easier to think about a
filtering operation in terms of what is removed, whereas for other
operations it makes more sense to think about what remains.

<File:Edge> Filter Before.png|A graph with all of its edges present...
<File:Edge> Filter After2.png|...then removed using a conditional filter
based on edge weight

### Transforms

#### Contract Edges

Remove edges which match the specified condition while simultaneously
merging the pairs of nodes that they previously joined. Often it is
superfluous to display two or more nodes that share a similar
characteristic; in this case we can use [edge
contraction](wikipedia:Edge_contraction "wikilink") to merge said nodes.

<File:Edge> Contraction Before.png|The orange edge will be contracted...
<File:Edge> Contraction After.png|...leaving nodes A and B merged

#### Contract By Attribute

Contract edges whose nodes share the same attribute value, such as
cluster name.

<File:Contract> By Attribute Before.png|Before <File:Contract> By
Attribute After.png|After

#### Edge Reduction

Reduce the complexity of the graph by removing a percentage of each
node's edges, down to a specified minimum. The remaining edges are a
representative sample of the original graph, but the result is
potentially less expensive to display. This transform is useful in the
case where [k-NN](#k-NN "wikilink") cannot be used because the graph's
edges do not have a rankable attribute such as a correlation
coefficient.

#### [k-NN](wikipedia:K-nearest_neighbors_algorithm "wikilink")

Reduce the number of edges in the graph using the [k-Nearest
Neighbours](wikipedia:K-nearest_neighbors_algorithm "wikilink")
algorithm. This is an approach where a node's edges are ranked in terms
of strength, on the basis of some attribute's value. Thereafter all but
the top *k* edges are removed. This has the effect of maintaining the
strongest relationships in the graph, and thus the structure, while
removing a large fraction of the edges. This can help in both visually
revealing otherwise hidden structure, and by reducing the computational
requirements for displaying the graph.

<File:K-NN> Before.png|Before <File:K-NN> After.png|After

#### %-NN

Reduce the number of edges in the graph using a variation of the
[k-Nearest
Neighbours](wikipedia:K-nearest_neighbors_algorithm "wikilink")
algorithm, but instead of choosing the top *k* edges, choose a
percentage of the highest ranking edges instead.

#### Remove Branches

Nodes that are only connected by a single edge are removed, iteratively.
This has the effect of removing all the branches (sometimes called
spurs) from the graph, leaving only cycles.

<File:Remove> Branches Before.png|Before <File:Remove> Branches
After.png|After

#### Remove Leaves

Like the Remove Branches transform, this removes singly connected nodes,
but only for a specified number of iterations. This means the branches
are pruned, but not removed completely.

#### Separate By Attribute

Remove edges whose nodes have different attribute values. This has the
effect of dividing a graph into components, where the attribute values
of the specified attribute are equal.

<File:Separate> By Attribute Before.png|Before <File:Separate> By
Attribute After.png|After

#### Spanning Forest

Every graph component has a sub-graph which is also a tree, meaning the
graph has no cycles. This sub-tree is created by starting at an
arbitrary node, and visiting each other node until all the nodes have
been observed. This process "spans" the entire graph and thus the new
graph is known as a [spanning tree](wikipedia:Spanning_tree "wikilink").
The graph can be visited by observing a child node and their siblings
first (known as [Breadth
First](wikipedia:Breadth-first_search "wikilink")), or by visiting a
child and the child's children in turn (known as [Depth
First](wikipedia:Depth-first_search "wikilink")). For a highly connected
graph, the former will tend to create "bushy" structures, whereas the
latter will result in "stringy" structures. This transform finds a
spanning tree for each component.

<File:Spanning> Tree Before.png|Before <File:Spanning> Tree
After.png|After