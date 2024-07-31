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

#### File Sharing Websites

Note that the resource link must be a direct link to the file in question. In particular sharing links as produced by sites such [Google Drive](https://drive.google.com/) are not suitable, as they end up on a landing page with a user clickable download button. Depending on the site in question there may still be a way to get a suitable direct file link, e.g. by right clicking the *Download* button and selecting *Copy Link Address*, or using a third party site that generates direct links from sharing links. The bottom line is that if the link can be pasted into a web browser and the download starts immediately, it should be suitable for Graphia.

#### Cross-Origin Resource Sharing

Modern web browsers implement a [security scheme](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) that restricts access to remote web resources that are served from a different domain to that of the requesting web site. This poses a problem for Graphia in that to open a shared resource it will invariably need to access files hosted on remote domains. In the general case, the web version of Graphia deployed at [https://web.graphia.app](https://web.graphia.app) uses a so called *CORS proxy* to mitigate this issue, passing all requests through a server that adds the appropriate headers in the reply, avoiding the problem entirely. It should be noted however that this is a facility that is not guaranteed to always exist, in particular if bandwidth constraints make it uneconomic to keep running, it may be disabled. As such if you are planning to use the web version at scale, with graph resources on a web site you control, in the first instance we suggest you deploy your own copy of web Graphia, avoiding CORS issues entirely. Failing that, you are strongly encouraged to ensure the correct CORS headers are present in order that use of the proxy server is avoided. Ultimately, this means that your web server should have the *Access-Control-Allow-Origin* header set in any reply that it makes to web Graphia. One or other of the following HTTP reply headers should suffice:

```
Access-Control-Allow-Origin: *
Access-Control-Allow-Origin: https://web.graphia.app
```

{% include guide-nav.html %}
