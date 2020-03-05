---
title: Loading Numerical Data
---

For datasets of numerical values arranged in columns and rows, it may not be obvious what the relationship between them is. Using Graphia’s built-in correlation analysis you can identify relationships between entities based on the similarity between their data patterns.  Graphia can rapidly generate correlation graphs even from very large tables of numbers, i.e. 10’s thousands or columns and rows. The process of preparing data for loading is down to the individual, as each data type or source of data may have its own challenges in getting it ‘graph ready’. These include; data cleaning, formatting, QC, normalisation, annotation, correction, imputation, etc.  Garbage in = Garbage out.

In order to leverage correlation analysis the data must be formatted into a either a Comma Separated Values (.csv), Tab Separated Values (.tsv) or an Excel Files (.xlsx). These files must be structured to be ‘correlation-ready’.

![]({{ site.url }}/guide/assets/s4-1.png)
Format of a ‘correlation analysis ready’ file and saved as a .csv file

A correlation-ready file consists of a header of column IDs, then a series of rows with each row representing a node (or entity). The first column should be a unique identifier for each entity. The next set of columns should describe attribute values associated with that entity. The final set of columns should be the numerical attribute data which will be used to perform the correlation analysis. Similarly columns of data should begin a unique identifier (row 1), include attribute data (where available), followed by the numerical values.

For a more in-depth look at the correlation-ready structure please view our wiki.

Once your data is correlation-ready, simply open the file in Graphia by navigating to File > Open or by clicking the file open icon. 

Below we have sought to describe the process and functions that might be used during any graph-based analysis. 

### Generation of correlation graphs

Where data of interest comprises of a table or spreadsheet of numerical values, calculation of a correlation matrix generates a relationship matrix between individual data series.  Most commonly this will be a case of generating a similarity matrix based on the Pearson correlation coefficient or perhaps Spearman rank, both of which can be calculated by Graphia. In principle, however, any relationship matrix based on a measure of similarity can be visualised within the tool. For instance, when dealing with categorical data use of Jaccard similarity coefficient is more appropriate. Other, measures may be calculated outside of the tool and imported as a similarity matrix.

In order to turn numerical data into a graph and identify data patterns and trends therein, Graphia compares the numerical values (data series) associated with each entity, with those associated with every other entity, in an all vs. all comparison. In other words, it calculates a correlation matrix where correlations range from -1 (perfect anti-correlation) to +1 (perfect correlation). The bigger the data series, i.e. the number of dimensions it contains, the less likely any entity will be correlated to another purely by chance. 

Upon loading a table of numbers, you will be presented with the Introduction dialog and informs that you are to enter Graphia’s Correlation plugin. To set up an analysis you will be guided through a number of other dialogs that set up the parameters for the analysis. Upon clicking next, you will be presented with the Data Selection dialog.

### Data selection dialog

![]({{ site.url }}/guide/assets/s4-2.png)
Data selection dialog with a numerical frame selected highlighted in blue and transpose option framed in red.

The Data Selection dialog contains a number of options to adjust the graph output from the file. Graphia automatically detects where the numerical data begins, i.e. the data frame (highlighted) from the input file.  You can click on cells within this page to add or remove rows and columns from the analysis if the data frame has not been selected as desired.

This page also gives you the option to transpose the data, if you wish to set the columns to be treated as nodes, instead of the rows. Click Next when happy with your selection.

### Correlation dialog

![]({{ site.url }}/guide/assets/s4-3.png)
Plot of predicted graph size based on correlation threshold. As initial threshold increases, the number of nodes and edges in the resultant graph decreases.

The distribution and number of correlation values for a given dataset is defined primarily by a number of variables:
- Number of dimensions (columns) – the smaller the number, the more likely things are correlated purely by chance, i.e. you will need to select a high r-threshold value. 
- Data structure – if there are many patterns in the data it will increase the number of highly connected cliques in the data and therefore the number of edges. Also if the data describes the same or similar entities many times over, edge numbers may again be very high. 
- Noise – the noisier (more random) a dataset the less it will correlated.
- Number of rows – this directly influences the absolute number of calculations that need to be performed but not the distribution of results.

A plot of node and edge counts for a range of threshold values is provided. It should be noted that the distribution of correlation values is dataset specific and one must be aware of those node and edge counts, correlation graphs are potentially massive! Given the dataset-specific nature of a correlation matrix, it is therefore necessary to select the Minimum and Initial thresholds for graph construction.

The Minimum Threshold describes the lowest correlation value that can be used to construct a graph, i.e. the minimum edge weight. Whilst Graphia calculates a full all vs. all correlation matrix it only saves some of the calculations. The reason being that when the input files are large (10’s thousands of rows), the number correlations calculated can be massive and storing them all will likely use up all of your RAM, and secondly, weak correlations are generally not interesting. Any correlation values below the minimum threshold will be discarded, while correlation values above the minimum threshold will be saved in memory for the duration of an analysis. Generally, the default minimum threshold of 0.7 is good for many applications. For datasets consisting of weakly correlated entities you may wish to lower this value or for strongly correlated matrices raise this value.

The Initial Threshold is used to set the minimum edge weight used for graph assembly. For example, using an initial threshold of r = 0.85 means entity pairs with a correlation score of 0.85 or above will be connected by an edge, while any relationship below r = 0.85 correlation will not be visible. The initial threshold can be changed later when the graph is generated. Clicking on and dragging the dotted line will adjust the Initial threshold or the value can be changed in the box. With initial threshold, a good starting point is to select a value near to the “Knee” of the plot; where the number of nodes begins to decrease more rapidly. In the example above this would be around 0.95. This choice is not permanent and can be adjusted later. Generally, the aim is to plot the maximum number of nodes connected by a minimum number of edges.

For most applications, the Pearson correlation coefficient is recommend with graphs being constructed based on all correlations above a defined threshold (out of distribution ranging from -1 to +1).  However, Graphia will also build correlation graphs based on Spearman Rank correlations and provides the option to build graphs of negative correlations or both negative and positive correlations.

Once thresholds are selected click Next.

### Data manipulation dialog
This provides a number of options to adjust the data values contained within your selected data frame.

![]({{ site.url }}/guide/assets/s4-5.png)
This dialog provides the means to impute, log/antilog transform or normalise input data prior to the calculation of the correlation matrix.
- Imputation (only displayed when needed) allows you to replace missing values in the dataset (empty cells) with a constant or interpolated value.
- Scaling scales the values within the data-frame, this is useful if you use logarithmic or exponential data.
- Normalisation allows you to adjust distributions of data within your data-frame. Min-Max normalisation is particularly useful if your columns each use different units.

If these settings are adjusted you may want to return correlation dialog to see what effect this has had on the distribution of correlations.

### Initial transform dialog
This dialog allows you to pre-add some of the most common transforms to the graph. Transforms can be added or removed later once a graph has been generated.

![]({{ site.url }}/guide/assets/s4-6.png)
This dialog provides the means to apply graph transforms prior to visualisation of the graph.

### Summary dialog
This dialog provides a look at all the parameters set before correlation occurs. These options can be copied and pasted for provenance of your analysis. 

![]({{ site.url }}/guide/assets/s4-7.png)
The Summary dialog lists all the pre-analysis data transforms that have been applied during the previous steps.

Please note: Should your selected settings for graph construction result in a massive graph, i.e. one that is likely to exhaust your computer’s memory or graphics card, usually because of the number of edges above the initial threshold, the following message will be displayed:

> ‘WARNING: This is a very large graph which has the potential to exhaust system resources and lead to instability or freezes. Increasing the Minimum Correlation Value will usually reduce the graph size.’ 

Ignore this warning at your peril!

Finish begins the computation of the initial graph visualised using settings provided by the user.

Clicking Confirm at any point during data entry will skip to the Summary dialog using default settings.