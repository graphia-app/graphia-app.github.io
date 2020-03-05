## First start-up

Once running Graphia, you will be greeted with an introductory dataset and a simple tutorial. This tutorial dataset uses a graph of the London Underground and Riverbus Networks. The tutorial will guide you through simple interactions with the graph. Once closed, you can reopen the tutorial by going to Help -> Show Tutorial.

## Graphia’s user interface

The user interface (GUI) of Graphia is designed to facilitate the visualisation and analysis of a variety of different data types. It is comprised of two or three windows (depending data type loaded) that can be viewed together (as below) orseparated to perhaps run across two screens.

## Graph visualisation window

Central to the UI is the graph visualisation window, wherein data is displayed in the form of a graph. Within this context data can be explored, selected, removed, searched and visualised. Millions of data points and relationships can be viewed at one time, or small areas of the graph may be focused upon.

Within the graph visualisation window, you can also access the Add Transforms(top right) and view/edit active transformations or Add Visualisations (bottom right) and view/edit active visualisations. Also displayed here are the summary statistics for the graph displayed (bottom left) and when active, search menusare placed in the top right-hand corner.

TO-DO: IMAGE
Graphia’s user interface displaying tutorial graph (London Transport Network).The nodes highlighted in green in the centre of the screen have been selected,the attribute table below showing their name and attributes. Clicking on a nodewithin this table selects nodes, without unselecting others.

## Node attribute table

The node attribute table (by default positioned at the bottom left of the graph visualisation window) displays information on selected nodes, their name and attribute information, whether imported or calculated within the tool. Columns of data can be hidden from view and selections exported as a table. In the case of 
the tutorial data, each node is associated with the name of a station plus some additional calculated attributes based on the generated graph. Node degreedescribes how many edges are connected to the node. Node multiplicitydescribes how many nodes are represented by this node. In the tutorial dataset each node will just reflect one station

TO-DO: IMAGE
Node attribute table for the London Underground map

## Toolbar
Along the top left of Graphia’s UI is a tool bar, listing a range of standard and graph specific functions. Many of these functions can also be accessed through use of hotkeys or via other windows.

Graphia’s UI also contains numerous notes and tool tips to help inform users about its many functions and features.

TO-DO: IMAGE
Hover over menu item or question mark symbols within Graphia to display moreinformation about a feature.

## Setting visual preferences

Once loaded the first step is graph layout, whereby the data is displayed in a manner designed to make it understandable to a user.  Graphia uses a custom force-directed layout algorithm and the results of each iteration of the algorithm are displayed to the user in a dynamic manner.  Graphia’s layout algorithm can be used to display even massive graphs quickly, defining the position of nodes and edges in 2- or 3-dimensional space.  Graph layout can be adjusted or pausedto optimise data visualisation (top left, Layout menu).  Similarly, the size and colour of nodes and edges may be set to suit the preferences of the user and/or dataset of interest (Settings tab - cog icon).

## Graph visualisation options

Graphia supports graph visualisation in 2D and 3D environments. Options for setting visualisation mode are found towards the bottom of the View menu. The default setting is display (layout) graphs in 3D and to use smooth 3D shading (A).  This view can be changed to flat shading while still displaying the graph in 3D (B). Orthographic view makes all node the same size but still rendered in 3D, perspective of distance is not applied – useful when displaying encodings using node size to distinguish between attributes in a 3D setting (C). Layout of a graphin 2D can be with smooth (D) or flat shading (E) and when node density is high, node/edge outline tracing (flat view only) helps visualisation (F).

Different graph visualisation options. (A) 3D perspective view, smooth shading (defaultview); (B) 3D perspective view, flat shading; (C) 3D orthographic view, flat shading; (D)2D view, smooth (3D) shading; (E) 2D view, flat shading; (F) compressed 2D layout, flatshading, showing node overlap view.

## Graph Navigation 
Graphs may be large and complex structures. To understand such complexity a user needs to be able find their way around them.  Graphia allows a user to view a graph from any angle, zoom in on a given node or pan out or view a graph as a whole.

Core to Graphia’s interface is the graph visualisation window. From here you can interact with the graph directly using your mouse. The nodes within the tutorial dataset are station and the edges are link between them.

- Rotate the graph, press the left mouse button and drag.
- Move the graph, press right mouse and drag.
- Zoom in or out, using the mouse wheel

There are two graph visualisation modes. Overview Mode provides a view of the entire graph and all its components. Component Mode provides a focused view at a particular graph component or a node within it. For example there are two components contained within London Transport graph, one is the London tube map, the second is the Riverbus network. These are displayed as separate components in overview mode as they are not connected to each other.

TO-DO: IMAGE
Overview mode on the left. Component mode on the right, focused on a particularcomponent. To move between components use arrows on left and right of the screen, toreturn to overview mode click on the icon on the bottom of the screen (red oval).

You can interact with nodes by clicking on them.

- Focus on a specific node, double click it.
- Select Single Nodes in the graph, press left mouse button on node.
- Select Multiple Nodes in the graph, press and hold Shift, then drag a selection rectangle around nodes.
- View a Component (multi-component graphs only) double click on a component of interest.
- Exit Component Mode and return to overview mode, click the back arrow at the bottom of the screen or press Esc.
- Right click nodes to bring up the context menu for additional actions.

TO-DO: Image
Context menu for Paddington station

## Searching for information within a graph

You may start an analysis with a predefined set of questions, want to look for entities you already know something about or simply search for things of interest. Graphia has a range of functionality to allow you to do this; to search fora given entity, to find entities with a given attribute, to understand their position within the graph or understand the local context within which they lie.  Go to Edit menu and select search option you require.

## Example Data

We provide a number of example files for you to download and explore within Graphia available on our Example data page.

