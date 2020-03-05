---
title: Enrichment Analysis
---

Enrichment Analysis is often useful especially when used in combination with graph clustering. Graphia provides a powerful enrichment tool built-in for testing your data.

Enrichment analysis is an additional test that can be performed on sets of data to identify how significant the set distribution is compared to an average. Imagine 4 red and 4 blue balls distributed between 2 sets randomly. The statistical likelihood is that each set should get 2 red and 2 blue balls. If a bag had 4 red balls in they would be “Enriched” in red balls since it is unlikely to occur by chance. It is a useful tool for understanding how likely a result is.

![]({{ site.url }}/guide/assets/s3-10.png)
The sets on the left are the statistical average layout, with 50% red and 50% blue. The sets on the right are said to be “enriched” in red and blue respectively as they contain 100% red or 100% blue, deviating from the statistical average.

With a dataset loaded within Graphia, Enrichment is located under “Tools > Enrichment“. This will bring up the Enrichment wizard. The enrichment wizard will walk you through the steps to get started.

The first attribute you be asked to select will define the “sets” to test for enrichment. This is most likely to be a clustering, e.g. MCL. The second attribute you will be asked to select will be the attribute value to test for enrichment. In the example above this would be the colour of the balls.

When completed, you will be prompted with the Enrichment Results dialog. This will display a table of results and a heat-map representation of the enrichment testing on the right.

![]({{ site.url }}/guide/assets/s3-11.png)
The table will display the comparison, the observed amount, the expected average and the over-representation factor. The amount of over-representation within the set (compared to the average) is displayed in the “Representation” column. The Fisher’s column is the Fisher's exact test results for that comparison. The adjusted Fisher’s is simply the Fisher’s value scaled by the number of different groups found within the set.

The heatmap displays the adjusted fisher's p-value in an easy to use form. Click a heatmap result to highlight the table entry. Only statistically significant values are coloured within the heatmap, values below the 0.05 threshold are grey.
By default only the **significant enriched** results are displayed in the table. To show all enrichment results, regardless of significance click the icon in the top left of the results window.
