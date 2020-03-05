While Graphia has the ability to load a wide variety of Graph based
formats, one of the important features within Graphia Enterprise is the
ability to perform a correlation analysis on numerical data. This
features allows relationships to be identified within the data-set that
were previously unseen. This capability is provided in Graphia
Enterprise by the Correlation Plugin.

This page aims to give you an overview of creating your own correlation
compatible file, performing your own correlation analysis and the
process of exploring your own Graph.

## Pearson Correlation

Graphia Enterprise uses a Pearson correlation to identify relationships
within a numerical data matrix. The Pearson correlation analysis will
compare data between each row of the data and assign a correlation value
between the two. 0 - 1, 0 being no correlation, 1 being very highly
correlation. This correlation value represents how similar the data
profile is between two rows (Nodes). A graph will then be created using
this information, with each row being a Node and each Edge being
correlation values over a specified threshold.

For more information on Pearson correlation, [click
here](wikipedia:Pearson_correlation_coefficient "wikilink").

## Formatting

![Simple_Numerical_Dataset.png](Simple_Numerical_Dataset.png
"Simple_Numerical_Dataset.png") In order for numerical data to be
eligible for correlation analysis by Graphia Enterprise, the data must
first be formatted correctly. The base format is a .csv or .tsv file
with data placed in a particular order. The minimum recommended amount
of information required for an analysis is **RowIDs, ColumnIDs,** and
**Data matrix**.

Excluding headers, each row represents a Node. With each column
representing either a row attribute (meta data), or a numerical data
sample for that Node.

###### ColumnID

Column Ids are used to identify the contents contained in the column
below. Column Ids need to be unique. They can consist of any character.
An example would be "Food Name".

###### Row Id / Node Id

Row Id's (or alternatively Node Ids) are used to identify the row of
data. They must be unique. They can consist of any character. An example
would be "Brown Bread".

###### Numerical Data Matrix

This should be any number of contiguous columns, containing only
numerical characters or empty values (excluding the ColumnID). This is
the data on which a pearson correlation analysis will be based.

###### Row Attributes (Optional)

Row attributes are additional columns placed between the row ids and the
numerical data matrix. They represent additional data (metadata) for
that node and can consist of any characters. This information will not
influence the output of a pearson correlation analysis but will be
included in the resultant graph as part of a node. As an example a Row
attribute ID could be Description of food and the example entry might be
"A bread made from wholewheat
flour"![Data_file_format.png](Data_file_format.png
"Data_file_format.png")

###### Column Attributes (Optional)

Column Attributes are additional rows placed above the data matrix, but
below ColumnIDs. This represents additional data (metadata) for that
numerical matrix sample column. As an example, column attribute "Time of
sample" could be an ID (placed above RowID but below ColumnIDs) and
potential entries above the data matrix columns could be "12:00" "15:00"
"18:00". Column attributes are mostly used to group similar sample
columns together visually when looking at results.

A simple example of a minimum compatible dataset could be nutritional
data of food. In this example the first column would have a header
(ColumnID) which would reflect the content of the first column, such as
"Food Name". Each column should then have a header that labels the data
contained within that column. For the data matrix in this example, the
headers would be Protein, Energy (Kcals), Starch etc.

Once the ColumnID row has been established, each row beneath represents
a Node of the final graph. The first column represents the **RowID**.
The columns after can be, *if required* **Row Attributes**. The columns
after are the **numerical** **data matrix**, this can be as many columns
as required however all data must either be numerical or empty. It
cannot contain any non-numerical data.

## Loading

When loading a correlation compatible file, Graphia Enterprise will give
you the option to load the file in a few different ways. When opening a
correlation file, select "Correlation CSV/TSV file" from the pop-up to
load a file in the correlation plugin.

After this, you'll be provided with the Correlation Parameters dialog.
This dialog contains a number of data pre-processes that can be applied
to your dataset. We will just be discussing the more important
pre-processes of correlation analysis.

### Data Selection

This page gives you the option to adjust the data matrix frame start.
Graphia automatically detects where the numerical data matrix begins in
the data, however if numerical row attributes columns are positioned
directly next to the data matrix they can be wrongly included in the
data matrix. This page also gives you the option to transpose data.

### Correlation - Adjust Thresholds

![Correlation_Threshold_dialog.png](Correlation_Threshold_dialog.png
"Correlation_Threshold_dialog.png")From here, two thresholds are able to
be adjusted. **Minimum** and **Initial** Threshold. Any correlation
value below the **Minimum Threshold** will be not be included in the
resultant Graph and will not create an edge. This is used to eliminate
extremely weak relationships, which you do not wish to observe. Any
correlation values above the minimum threshold will persist in the Graph
and will be used to create edges. **Initial Threshold** describes the
minimum correlation value required for Edge to be displayed, i.e An
initial threshold of 0.8 means edges with a correlation value of 0.8 or
above display an edge, any relationships below 0.8 correlation value
will not be visible. The Initial Threshold can be changed dynamically
later when the graph is created.

Graphia will provides a plot of of Node and Edge counts for a range of
threshold values. The default values are a good baseline to begin your
investigation, but it is worth observing the plot to evaluate if your
edge count will massively exceed Node count and adjust accordingly. As a
general rule of thumb, the point at which Edge counts begin to decrease
substantially is good **Initial threshold** starting point.

After this, you can confirm and finalise the settings and Graphia will
begin to generate your graph.

## Correlation Graph

![Initial_Correlation_Graph.png](Initial_Correlation_Graph.png
"Initial_Correlation_Graph.png") Once all parameters are confirmed, a
Graph will be created. Each Node represents a row of data from your
data-set and each edge will represent a relationship that is equal to or
above your Initial correlation threshold.

Two transforms will be automatically added to the graph. "*Remove edges
where Pearson Correlation Value \< \[Initial Threshold\]*" and "*Remove*
*Components where Component Size \<= 1*"

All correlation values that are above the **Minimum** Threshold Value
from the loading step are transformed into Edges in the graph. *"The
Remove edges where Pearson Correlation Value..."* transform allows you
to adjust the cut-off point at which Edges are removed. By adjusting the
threshold using the slider up, you can remove less correlated edges and
only preserve the most correlated relationships. By adjusting the value
you down, you create edges from less similar data. Changing this value
will alter the overall shape of the graph, and is a useful tool for
filtering relationships.

The "*Remove* *Components where Component Size \<= 1*" will remove
individual, unconnected nodes from the display. This can be disabled or
deleted if the information is still required.

Below the graph view, is the Correlation data viewer. This is a specific
to the Correlation plugin. This can be used to inspect data within
selected nodes in a Graph.
![centre](Inspecting_data_in_a_correlation_Graph.png "centre") The table
on the left displays Node attribute data, this is data that was
contained within the "Row attribute" section of the dataset. On the
right, the profile viewer consists of a plot created from the numerical
matrix data provided. By selecting multiple nodes, you can compare
profiles directly and hover over for exact values. This helps identify a
cause for the relationship between nodes.

### Transforming the Graph

From this point, you can begin adding transforms to better explore the
data. One of the more useful transforms is the **MCL Cluster**
transform. By clicking *Add Transform* and adding **MCL Cluster** to the
graph, the Graph will be clustered into groups of various sizes. This
helps identify groups of nodes which are similar based on the structure
within the graph. This transform adds an attribute to each node,
describing the cluster it belongs to. This is then shown with a colour
visualisation which is automatically added. This transform has an
adjustable parameter called "Granularity" which adjusts the size of the
clusters.

**PageRank** transform adds an attribute that can be used to rank the
importance of the nodes in the overall structure. **Eccentricity** can
also be added, which adds another attribute which represents how central
a node is in the overall structure. Node attributes can be visualised
through the use of visualisations.