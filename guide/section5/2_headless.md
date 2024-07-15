---
title: Headless Operation
prev: 1_webassembly
---

{% include guide-nav.html %}

## Use Cases

The normal process for visualising a graph from source data is to open said data in the desktop application, set all the required options, and then wait for it to be processed. For one off invocations this is fine, but in the case where there are many source files that all need the same treatment, it is advantageous to do this processing in batch, avoiding the tedium of manually loading each one individually.

Alternatively, it is often the situation that the data fed into Graphia is the result of an external pipeline written in a data processing language such as [R](https://www.r-project.org/) or [Python](https://www.python.org/). Such things are often run repeatedly, iteratively tweaking data and/or parameters. Again, in such a case the final loading step in Graphia is likely invariant and tedious to repeat manually. It is useful to process the results "offline", producing an output that is immediately usable in Graphia.

## Headless

Both of these use cases are catered for with Graphia's "headless" mode. When this is employed Graphia is accessed as a command line tool, and the parameters described by a JSON file.

```
Options:
  -h, --help               Displays help on commandline options.
  --help-all               Displays help, including generic Qt options.
  -u, --dontUpdate         Don't update now, but remind later.
  -m, --startMaximised     Put the application window in maximised state.
  -w, --skipWelcome        Don't show the welcome screen on first start.
  -p, --parameters <file>  Run in headless mode, using parameters from <file>.
```

The command line argument we are interested in here is `-p` or `--parameters` which is used to specify the JSON parameters file for offline processing. As an example Graphia may be invoked (on Linux) as follows:

`./Graphia.AppImage --parameters pearson-correlation.json data_file.csv`

The `pearson-correlation.json` file might look like:

```
{
    "type": "CorrelationCSV",
    "plugin":
    {
        "name": "Correlation",
        "parameters" :
        {
            "minimumThreshold": 0.7,
            "initialThreshold": 0.85,
            "continuousCorrelationType": "Pearson",
            "normalise": "MinMax",
            "additionalTransforms": ["\"Louvain Cluster\" with \"Granularity\" = 0.5"],
            "additionalVisualisations": ["\"Louvain Cluster\" \"Colour\""]
        }
    }
}
```

This will perform a standard Pearson correlation on `data_file.csv`, min/max normalised. The graph will have a Louvain clustering performed, and an associated visualisation applied. The output will then be written to `data_file.graphia` which can subsequently be opened by Graphia, in GUI mode. The general form of the parameters file is as follows (note that inline comments are not supported by JSON; they're only present to document):

```
{
    // What type to interpret the input file as
    "type": "FileType",

    // If omitted, the file name(s) are generated based on the input file name
    "destination": "/optional/destination/file/or/directory",

    "plugin":
    {
        // The name of the plugin to use for loading
        "name": "PluginName",

        // The parameters to use with the selected plugin
        "parameters":
        {
            // See below
            ...
        }
    }
}
```

#### Type Field

| Type | Description |
| --- | --- |
| BiopaxOWL | [Biopax OWL](http://www.biopax.org/owldoc/Level3/) |
| CorrelationCSV | Correlation Command Separated Values |
| CorrelationSSV | Correlation Semicolon Separated Values |
| CorrelationTSV | Correlation Tab Separated Values |
| CorrelationXLSX | Correlation Microsoft Excel |
| CX | [Cytoscape Exchange](https://home.ndexbio.org/data-model/) |
| DOT | [Graphviz DOT](https://www.graphviz.org/doc/info/lang.html) |
| GML | [Graph Modelling Language](https://github.com/GunterMueller/UNI_PASSAU_FMI_Graph_Drawing/blob/master/GML/gml-technical-report.pdf) |
| GraphML | [GraphML](http://graphml.graphdrawing.org/primer/graphml-primer.html) |
| JSONGraph | [JSON Graph](https://jsongraphformat.info/) |
| MatrixCSV | Matrix Command Separated Values |
| MatrixMatLab | Matrix in MatLab MAT-file |
| MatrixSSV | Matrix Semicolon Separated Values |
| MatrixTSV | Matrix Tab Separated Values |
| MatrixTXT | Matrix Text (Space Separated Values) |
| MatrixXLSX | Matrix Microsoft Excel |
| PairwiseCSV | Pairwise Command Separated Values |
| PairwiseSSV | Pairwise Semicolon Separated Values |
| PairwiseTSV | Pairwise Tab Separated Values |
| PairwiseTXT | Pairwise Text (Space Separated Values) |
| PairwiseXLSX | Pairwise Microsoft Excel |

#### Plugin Name Field

| Name | Description |
| --- | --- |
| Correlation | Build a graph based on relationships between rows of data |
| Generic | Load data that's already directly interpretable as a graph |
| WebSearch | As Generic, but showing a website in place of the data table |

## Plugin Parameters

For a detailed description of the meaning of the below parameters, consult the inline help in the respective loader dialogs.

### Generic/WebSearch

#### Pairwise Only

| Name | Type | Possible Values/Description |
| --- | --- | --- |
| firstRowIsHeader | Boolean | If true, the first row is treated as a header row, otherwise it counts as data |
| columns | Object | In the pairwise data case, this describes the role of each column where the type field is one of 0 (Unused), 1 (Source Node), 2 (Target Node), 3 (Edge Attribute), 4 (Source Node Attribute) or 5 (Target Node Attribute), e.g. { "0": { "type": "1" }, "1": { "type": "2" }, "2": { "type": "3", "name": "Edge Weight" } } |

#### Matrix Only

| Name | Type | Possible Values/Description |
| --- | --- | --- |
| minimumThreshold | Float | 0.0 to 1.0 |
| initialThreshold | Float | 0.0 to 1.0 |
| filterEdges | Boolean | Filter edges according to selected thresholds if true |
| skipDuplicates | Boolean | Don't add both edges (from either side of the diagonal) if true |

#### Other

| Name | Type | Possible Values/Description |
| --- | --- | --- |
| additionalTransforms | Array | e.g. ["\\"Louvain Cluster\\" with \\"Granularity\\" = 0.5"] |
| additionalVisualisations | Array | e.g. ["\\"Louvain Cluster\\" \\"Colour\\""] |

### Correlation

| Name | Type | Possible Values/Description |
| --- | --- | --- |
| minimumThreshold | Float | 0.0 to 1.0 |
| initialThreshold | Float | 0.0 to 1.0 |
| maximumK | Int | ≥ 1 |
| initialK | Int | ≥ 1 |
| transpose | Boolean | Transpose the table if true |
| correlationFilterType | String | Threshold, Knn |
| correlationDataType | String | Continuous, Discrete |
| continuousCorrelationType | String | Pearson, SpearmanRank, EuclideanSimilarity, CosineSimilarity, Bicor |
| discreteCorrelationType | String | Jaccard, SMC |
| correlationPolarity | String | Positive, Negative, Both |
| scaling | String | None, Log2, Log10, AntiLog2, AntiLog10, ArcSin |
| normalise | String | None, MinMax, Quantile, Mean, Standardisation, UnitScaling, SoftMax |
| missingDataType | String | Constant, ColumnAverage, RowInterpolation |
| missingDataValue | Float | |
| clippingType | String | None, Constant, Winsorization |
| clippingValue | Float | |
| treatAsBinary | Boolean | Treat discrete data as binary if true |
| dataRect | Object | e.g. {"x": 0, "y": 1, "width": 10, "height": 10} |
| additionalTransforms | Array | See Generic/Other |
| additionalVisualisations | Array | See Generic/Other |

{% include guide-nav.html %}
