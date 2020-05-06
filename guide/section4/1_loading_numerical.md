---
title: Loading Numerical Data
---

## Numerical Data

For datasets of numerical values arranged in columns and rows, it may not be obvious what the relationship between them is. Using Graphia's built-in correlation analysis, you can identify relationships between entities based on the similarity between their data patterns. Graphia can rapidly generate correlation graphs even from very large tables of numbers, i.e. 10s of thousands of columns and rows. The process of preparing data for loading is down to the individual, as each data type or source of data may have its own challenges in getting it 'graph ready'. These include; data cleaning, formatting, QC, normalisation, annotation, correction, imputation, etc.. Garbage in = Garbage out.

In order to leverage correlation analysis the data must be formatted into a either a Comma Separated Values (.csv), Tab Separated Values (.tsv) or an Excel Files (.xlsx). These files must be structured to be 'correlation-ready'.

![]({{ site.baseurl }}/guide/assets/s4-1.png)
<div class="caption">Format of a 'correlation analysis ready' file and saved as a .csv file</div>

A correlation ready file consists of a header of column IDs, then a series of rows with each row representing a node (or entity). The first column should be a unique identifier for each entity. The next set of columns should describe attribute values associated with that entity. The final set of columns should be the numerical attribute data which will be used to perform the correlation analysis. Similarly columns of data should begin a unique identifier (row 1), include attribute data (where available), followed by the numerical values.

Once your data is in this form, simply open the file in Graphia by navigating to File → Open or by clicking the file open toolbar button. 

## Generation of Correlation Graphs

Where the data of interest is comprised of a table of numerical values, a correlation matrix is calculated, whereby both axes list the entities being compared, and the intersecting cells contain the correlation scores. In practice this matrix is unreasonably large and thus does not exist, but it can be helpful to conceptualise the process. Most commonly the scores in the similarity matrix are calculated using the Pearson correlation coefficient or perhaps Spearman rank, both of which can be calculated by Graphia. In principle however, any relationship matrix based on a measure of similarity can be visualised by the tool. For instance, when dealing with categorical data use of Jaccard similarity coefficient is more appropriate. Other measures may be calculated outside of the tool and imported as a similarity matrix.

In order to turn numerical data into a graph and identify data patterns and trends therein, Graphia compares the numerical values (data series) associated with each entity, with those associated with every other entity, in an all vs. all comparison. In other words, it makes a list of correlations ranging from -1 (perfect anti-correlation) to +1 (perfect correlation). The bigger the data series, i.e. the number of measurements it contains, the less likely any entity will be correlated to another purely by chance. 

Upon loading a table of numbers, you will be presented with the correlation wizard. To set up an analysis you will be guided through a variety of options that set up the parameters for the analysis. Upon clicking next, you will be presented with the Data Selection page.

## Data Selection

![]({{ site.baseurl }}/guide/assets/s4-2.png)
<div class="caption">Data selection page with a numerical frame selected highlighted in blue and transpose option framed in red.</div>

The Data Selection page contains a number of options to adjust the graph output from the file. Graphia automatically detects where the numerical data begins, i.e. the data frame (highlighted) from the input file. You can click on cells to add or remove rows and columns from the analysis if the data frame has not been selected as desired.

This page also gives you the option to transpose the data, if you wish to set the columns to be treated as nodes, instead of the rows. Click Next when happy with your selection.

## Correlation

![]({{ site.baseurl }}/guide/assets/s4-3.png)
<div class="caption">Plot of predicted graph size based on correlation threshold. As initial threshold increases, the number of nodes and edges in the resultant graph decreases.</div>

The distribution and number of correlation values for a given dataset is defined primarily by a number of variables:
- **Number of Columns** - the smaller the number, the more likely things are correlated purely by chance, i.e. you will need to select a high r-threshold value. 
- **Data Structure** - if there are many patterns in the data it will increase the number of highly connected cliques in the data and therefore the number of edges. Also if the data describes the same or similar entities many times over, edge numbers may again be very high. 
- **Noise** - the noisier (more random) a dataset the less it will correlate.
- **Number of Rows** - this directly influences the absolute number of calculations that need to be performed but not the distribution of results.

A plot of node and edge counts for a range of threshold values is provided. It should be noted that the distribution of correlation values is dataset specific and one must be aware of those node and edge counts, correlation graphs are potentially massive! Given the dataset specific nature of a correlation, it is therefore necessary to select the Minimum and Initial thresholds for graph construction.

The Minimum Threshold describes the lowest correlation value that can be used to construct a graph, i.e. the minimum edge weight. While Graphia calculates a full all vs. all correlation it only saves a subset the calculations as when the input files are large, the number of correlations calculated can be massive. Not only will this potentially exhaust system resources, weak correlations are generally not interesting. The default minimum threshold of 0.7 is good for many applications. For datasets consisting of weakly correlated entities you may wish to lower this value and vice versa for strongly correlated datasets.

The Initial Threshold is used to set the minimum edge weight threshold used for graph assembly. For example, using an initial threshold of 0.85 means entity pairs with a correlation score of 0.85 or above will be connected by an edge, while any relationship below 0.85 correlation will not. The Initial Threshold can be changed after the graph is generated. Clicking and dragging the dotted line will adjust the Initial threshold, or the value can be changed directly using the keyboard. With Initial Threshold, a good starting point is to select a value near to the "Knee" of the plot; where the number of nodes begins to decrease more rapidly. In the example above this would be around 0.95. Generally, the aim is to plot the maximum number of nodes connected by a minimum number of edges.

For most applications, the Pearson correlation coefficient is recommend with graphs being constructed based on all correlations above a defined threshold (out of distribution ranging from -1 to +1). However, Graphia will also build correlation graphs based on Spearman Rank correlations and provides the option to build graphs of negative correlations or both negative and positive correlations.

Once thresholds are selected click Next.

## Data Manipulation
This provides a number of options to adjust the data values contained within your selected data frame.

![]({{ site.baseurl }}/guide/assets/s4-5.png)
<div class="caption">This page provides the means to impute, log/antilog transform or normalise input data prior to the calculation of the correlation matrix.</div>

- Imputation (only displayed when needed) allows you to replace missing values in the dataset (empty cells) with a constant or interpolated value.
- Scaling scales the values within the data-frame, this is useful if you use logarithmic or exponential data.
- Normalisation allows you to adjust distributions of data within your data-frame. Min-Max normalisation is particularly useful if your columns each use different units.

If these settings are adjusted you may want to return to the correlation plot to see what effect this has had on the distribution of correlations.

## Initial Transforms
This allows you to add some of the most common transforms to the graph. Transforms can be added or removed later once a graph has been generated.

![]({{ site.baseurl }}/guide/assets/s4-6.png)
<div class="caption">This page provides the means to apply graph transforms prior to visualisation of the graph.</div>

## Summary
The final page provides a look at all the parameters set before correlation occurs. These options can be copied and pasted for provenance of your analysis. 

![]({{ site.baseurl }}/guide/assets/s4-7.png)
<div class="caption">The Summary lists all the pre-analysis data transforms that have been applied during the previous steps.</div>

Please note: Should your selected settings for graph construction result in a massive graph, i.e. one that is likely to exhaust your computer's memory or graphics card, the following message will be displayed:

> 'WARNING: This is a very large graph which has the potential to exhaust system resources and lead to instability or freezes. Increasing the Minimum Correlation Value will usually reduce the graph size.' 

Ignore this warning at your peril!

Clicking Finish begins the computation of the initial graph visualised using settings provided by the user. Clicking Confirm at any point during data entry will skip to the Summary page using the current settings.
