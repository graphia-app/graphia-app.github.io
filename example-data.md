Example Datasets
================

Below are a variety of datasets that can be used to explore Graphia's functionality. To learn more about creating your own supported file [visit the Wiki](https://kajeka.com/wiki/)

### **Mouse tissue expression atlas** – Comma Seperated Value (.csv)

This is the data set that started it all off. It is a microarray analysis of gene expression across a range of different mouse tissues. It consists of over 36,000 measurements taken across 122 samples (61 tissue and cells types) of embryonic and adult mouse samples. It represents one of the first ‘big’ gene expression data sets in biology and was originally published by Su et al. back in 1994 (PNAS, 101: 6062); the study has now been cited nearly 3,000 times. It was the frustrations of trying to analyse these data using conventional bioinformatics approaches that drove us to develop the network analysis approach incorporated into Graphia

[Download Mouse Tissue](https://kajeka.com/wp-content/uploads/2015/11/mouse_tissue_atlas.zip)

### **Nutritional Food Data** – Comma Seperated Value (.csv)

![](https://kajeka.com/wp-content/uploads/2015/11/nutrition.jpg)The figures included in tables on the side of food packaging contain only a fraction of the available nutrients that are commonly tested for. It is not uncommon for laboratories to test for over a 100 different nutrients in a given food product. This is a rich source of information, but when tested across many foodstuffs the amount of data becomes significant challenge to understand. Here we provide nutritional data from a wide variety of foods in a format ready for network analysis. The data comes from the UK Government’s Food Standards Agency website. After some data cleaning we have taken nutritional values for 948 foods and where available the results of 104 nutritional value scores. An analysis ready copy of these data are provided here.

[Download Food contents](https://kajeka.com/wp-content/uploads/2019/09/Food_contents_2019.csv)

### **Mouse Single cell Analysis** – Numerical Data (.csv)

This data originates from a study that analysed global gene expression in hundreds of individual mouse cells, from the oocyte to late blastocysts. As such the data describes the changing transcriptional landscape of individual cells undergoing the very earliest stages of embryonic development from an egg to a ball of cells. Whilst relatively small for single cell data (only 268 cells), it is a very well-known dataset often used for training purposes and bench-marking new techniques. It also allows you to explore the potential of Graphia for analysis of single cell data. Data from: Deng Q., et al. Single-Cell RNA-Seq Reveals Dynamic, Random Monoallelic Gene Expression in Mammalian Cells. [Science 343, 193-196 (2014).](http://science.sciencemag.org/content/343/6167/193.long) [Download Mouse single cell data](/wp-content/uploads/2019/02/Deng_assay.csv)

### **UK Forename Data** – Numerical Correlation Data (.csv)

Network analysis of the social and demographic influences on name choice within the UK (1838-2016). Chosen names reflect changes in societal values, personal tastes and cultural diversity. Patterns in name usage can be easily shown on a case by case basis, by plotting the rise and fall in their popularity over time. However, individual name choices are not made in isolation and trends in naming are better understood as group-level phenomena. In this study researchers used network analysis to examine naming records in order to explore the influences on name choices within the UK over the last 170 years. Using a large representative sample of approximately 22 million forenames from England and Wales given between 1838 and 2014, along with a complete population sample of births registered between 1996 and 2016, they demonstrated how trends in name usage can be visualised using Kajeka's software. Data from: Bush S.J., Powell-Smith A, Freeman TC (2018) Network analysis of the social and demographic influences on name choice within the UK (1838-2016). [PLoS ONE 13(10): e0205759.](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0205759) [Download Historical UK forename data](/wp-content/uploads/2019/02/UK_forenames_1838-2014.csv)

### **Mammal Taxonomy Graph** – BioLayout File (.layout)

Taxonomy is the science of classifying and categorising biological organisms within structured hierarchical groups. The resulting structure of taxonomic classification is a large spanning tree, which is ideal for 3D representation and exploration. Using data provided from the US National center for biotechnical information we have constructed a 3D graph of Mammalia within the animal kingdom. Each taxonomic rank within the hierarchy is represented as a unique class within the graph and is given a unique colour within it.

[Download Mammal Taxonomy Graph](https://kajeka.com/wp-content/uploads/2016/04/mammalTaxonomy.layout)

### **2008-2009 NASDAQ Shares** – Comma Seperated Value (.csv)

Share prices rise and fall based on the performance of the company, but their value is also subject to the vagaries of the market and external forces. 2008 witnessed the now famous crash of the stock market. Sept 15th was named ‘Black Monday’ after Lehman Brothers declared bankruptcy and the Dow dropped over 500 points. Following this, market uncertainty increased and bottomed on March 5th 2009. This data set from the NASDAQ Stock Market covers the period from the beginning of 2008 until then end of 2009. It lists the end of day prices (505 in total) of 2,615 companies and therefore covers the peak period of this bear market. Visualisation of correlation networks these data provide a unique interface to explore the events of a catastrophic market meltdown.

[Download NASDAQ](https://kajeka.com/wp-content/uploads/2015/11/NASDAQ-2008-2009.csv)

### **Finance256** – BioLayout File (.layout)

This is an example graph file provided by the University of Florida sparse matrix collection. This collection is used to test the layout capabilities of a variety of graph layout algorithms. The collection is designed to be particularly difficult for a stable optimum layout to be found. This graph is particularly large, however Graphia effortlessly provides an appealing layout

[Download Finance256](https://kajeka.com/wp-content/uploads/2016/04/finance256.layout)

### **London Tube map** – Simple Pairwise Two Column Text File (.txt)

This is an example of a simple Pairwise text file using two columns to represent connected tube stations in the London underground. The London tube map was originally the brainchild of electrical draughtsman, Harry Beck, who produced his imaginative and beautifully simple design back in 1933. It is now one of the most famous network diagrams in the world. Here we present the data used for it a connectivity map of stations and lines, as a simple node-edge relationship file for visualisation within Graphia.

[Download London Tube Pairwise](https://kajeka.com/wp-content/uploads/2015/10/Simple_pairwise-London_tube_map.txt)

### **Mouse Gene Clusters** – Weighted Pairwise Example (.txt)

A sub graph derived from Dataset 1 and saved as a simple weighted edge file format consisting of node-edge relationships and edge weight (3 column format). It is graph of mouse genes and their coexpression relationships to each other. The underlying data is however not saved with the graph.

[Download Mouse Gene Clusters](https://kajeka.com/wp-content/uploads/2015/10/Weighted_pairwise-gene-clusters.txt)

### **Cylinder graph** – (.gml)

A Cylinder shape provided in .gml format with a random series of "holes" within the structure, specifically to make optimum layout difficult

[Download Cylinder Graph](https://kajeka.com/wp-content/uploads/2015/10/cylinder_rnd_100_100.gml)

### **Blackhole** – Simple Pairwise Two Column Text File (.txt)

A "Black hole" shape provided by a simple pairwise connection of nodes in a text file

[Download Blackhole Pairwise](https://kajeka.com/wp-content/uploads/2015/11/Simple_pairwise-Blackhole.txt)

### **Flower** – (.gml)

A complex flower shape created in the .gml format provided by the Hachul graph set

[Download Flower](https://kajeka.com/wp-content/uploads/2015/11/flower_005.gml)