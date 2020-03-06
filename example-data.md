---
title: Example Datasets
published: true
---

Below are a number of example datasets from different sources and saved in a variety of supported formats that can be used to explore Graphia's functionality. If these load and your data doesn't you most likel have an issue with the file format.

## **Biology**

### **Mouse Tissue Expression Atlas** – Numerical Data Matrix (.csv)

This is the dataset that started it all off. It is a microarray analysis of gene expression across 61 mouse tissues. It consists of over 36,000 measurements taken across 122 samples of embryonic and adult mouse samples. It represents one of the first ‘big’ gene expression datasets in biology and was originally published by Su _et al._ back in 1994 [PNAS, 101: 6062](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC395923/). It was the frustrations of trying to analyse these data using conventional bioinformatics approaches that drove us to develop the gene correlation network analysis approach incorporated into Graphia.

[Download Mouse Tissue]({{ site.url }}/datasets/mouse_tissue_atlas.zip)

### **Mouse Gene Clusters** – Weighted Pairwise (.txt)

A sub-graph derived from GNF mouse atlas (above) and saved as a simple weighted edge file format consisting of node-edge relationships and edge weight (3 column format). It is graph of mouse genes and their coexpression relationships to each other. The underlying data is however not saved with the graph.

[Download Mouse Gene Clusters]({{ site.url }}/datasets/Weighted_pairwise-gene-clusters.txt)


### **Mouse Single cell Analysis** – Numerical Data Matrix (.csv)

These data describe the changing transcriptional landscape of individual cells sampled from a fertilised mouse egg (zygote) to a ball of cells (blastocyst). Whilst relatively small for single cell data (only 268 cells), it is a very well-known dataset often used for training purposes and bench-marking new techniques. It also allows you to explore the potential of Graphia for analysis of single cell data. Data from: Deng Q., _et al_.  [Science 343, 193-196 (2014).](http://science.sciencemag.org/content/343/6167/193.long)

[Download Mouse single cell data]({{ site.url }}/datasets/Deng_assay.csv)

### **Taxonomic Tree  of Mammals** – BioLayout File (.layout)

Taxonomy is the science of classifying and categorising biological organisms within structured hierarchical groups. The resulting structure of taxonomic classification is a spanning tree. Using data from the US National Center for Biotechnology Information (NCBI) [Taxonomy database](https://www.ncbi.nlm.nih.gov/taxonomy/) we have constructed a graph of mammals. Each taxonomic rank within the hierarchy is represented as a unique class within the graph and is given a unique colour within it.

[Download Mammal Taxonomy Graph]({{ site.url }}/datasets/mammalTaxonomy.layout)


## **Other data**

### **London Tube Map** – Two column pairwise (.txt)

Pairwise text file using two columns to represent connected tube stations in the London underground. The London tube map was originally designed by electrical draughtsman, Harry Beck, in 1933, is now one of the most famous network diagrams in the world. Here we present the data used for it a connectivity map of stations and lines, as a simple node-edge relationship file for visualisation within Graphia.

[Download London Tube Pairwise]({{ site.url }}/datasets/Simple_pairwise-London_tube_map.txt)

### **Nutritional Food Data** - Numerical Data Matrix (.csv)

It is not uncommon for laboratories to test for over a 100 different nutrients in a given food product. This is a rich source of information, and when results are collated across many foodstuffs the amount of data becomes significant challenge to understand. Here we provide nutritional data from a wide variety of foods in a format ready for network analysis. The data comes from the UK Government’s [ood Standards Agency] (https://www.food.gov.uk/) website. After some data cleaning we have taken nutritional values for 948 foods and where available the results of 104 nutritional value scores. An analysis ready copy of these data are provided here.

[Download Food contents]({{ site.url }}/datasets/Food_contents_2019.csv)


### **UK Forename Data** – Numerical Correlation Data (.csv)

In this study, Bush S.J., Powell-Smith A, Freeman TC (2018) Network analysis of the social and demographic influences on name choice within the UK (1838-2016). [PLoS ONE 13(10): e0205759.](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0205759), researchers used network analysis to examine naming records in order to explore the influences on name choices within the UK over the last 170 years. Using a large representative sample of approximately 22 million forenames from England and Wales given between 1838 and 2014, along with a complete population sample of births registered between 1996 and 2016, they demonstrated how trends in name usage can be visualised using Graphia software. 

[Download Historical UK forename data]({{ site.url }}/datasets/UK_forenames_1838-2014.csv)

### **2008-2009 NASDAQ Shares** – Numerical data (.csv)

Share prices rise and fall based on the performance of the company, but their value is also subject to the vagaries of the market and external forces. 2008 witnessed the now famous crash of the stock market. Sept 15th was named ‘Black Monday’ after Lehman Brothers declared bankruptcy and the Dow dropped over 500 points. Following this, market uncertainty increased and bottomed on March 5th 2009. This data set from the NASDAQ Stock Market covers the period from the beginning of 2008 until then end of 2009. It lists the end of day prices (505 in total) of 2,615 companies and therefore covers the peak period of this bear market. Visualisation of correlation networks these data provide a unique interface to explore the events of a catastrophic market meltdown.

[Download NASDAQ]({{ site.url }}/datasets/NASDAQ-2008-2009.csv)


## **Geometric Graphs**

### **Cylinder graph** – (.gml)

A Cylinder shape provided in .gml format with a random series of "holes" within the structure, specifically to make optimum layout difficult

[Download Cylinder Graph]({{ site.url }}/datasets/cylinder_rnd_100_100.gml)

### **Blackhole** – Simple Pairwise Two Column Text File (.txt)

A "Black hole" shape provided by a simple pairwise connection of nodes in a text file

[Download Blackhole Pairwise]({{ site.url }}/datasets/Simple_pairwise-Blackhole.txt)

### **Flower** – (.gml)

A complex flower shape created in the .gml format provided by the Hachul graph set

[Download Flower]({{ site.url }}/datasets/flower_005.gml)

### **Finance256** – BioLayout File (.layout)

Example graph file provided by the SuiteSparse Matrix Collection [formerly the University of Florida Sparse Matrix Collection] (https://sparse.tamu.edu/about). This collection is used to test the layout capabilities of a variety of graph layout algorithms. The collection is designed to be particularly difficult for a stable optimum layout to be found. This graph is particularly large!

[Download Finance256]({{ site.url }}/datasets/finance256.layout)
