---
title: WebAssembly Support
next: 2_headless
---

{% include guide-nav.html %}

## WebAssembly

Graphia is available in [WebAssembly form](https://web.graphia.app), that is to say it can be run directly within a modern web browser. It is broadly speaking functionally equivalent to the desktop version, albeit with restrictions; in particular:
- The scale of the graph that can be loaded is lesser (there is a 2Gb memory limit)
- Only a subset of compute resources are used so long running algorithms are slower
- Additionally, said compute resources are less efficiently used
- The visual fidelity of the graph display is relatively lacking
- Loading and saving files is generally less streamlined

For serious tasks therefore, we recommend downloading [the desktop version]({{ site.url }}/download.html), but for casual usage the web version may be perfectly adequate.

![]({{ site.url }}/guide/assets/webassembly.png)

## Sharing

Having Graphia available on the web allows for easy sharing of graph analyses. Arguments can be passed via the URL, equivalent to the command line arguments of the desktop version. More specifically, the `arguments` HTTP POST key can be set with one or more values. In the case where multiple arguments are required, these are separated by a `+`. Graphia can download and open files from the web and as such a web resource can be opened via this method. For example, given the resource [https://graphia.app/datasets/flower_005.gml](https://graphia.app/datasets/flower_005.gml), a direct web link can be created by appending it to `https://web.graphia.app/?arguments=`:

[https://web.graphia.app/?arguments=https://graphia.app/datasets/flower_005.gml](https://web.graphia.app/?arguments=https://graphia.app/datasets/flower_005.gml)

Note that the resource link must be a direct link to the file in question. In particular sharing links as produced by sites such [Google Drive](https://drive.google.com/) are not suitable, as they end up on a landing page with a user clickable download button.

{% include guide-nav.html %}
