---
title: Download
---

<div class="downloads">
<h3 id="graphia-for-windows" class="download-button-wrapper">
<a class="download-button" href="{{site.downloads.windows}}">Windows Installer</a>
</h3>
<h3 id="graphia-for-macos" class="download-button-wrapper">
<a class="download-button" href="{{site.downloads.macos}}">MacOS Disk Image</a>
</h3>
<h3 id="graphia-for-linux" class="download-button-wrapper">
<a class="download-button" href="{{site.downloads.linux}}">Linux AppImage</a>
</h3>
</div>

<div class="downloads">
<p><a href="{{site.downloads.source}}">Source Code</a></p>
<p><a id="show-other-platforms" href="#">Other Platforms</a></p>
</div>

<script>
function hide(element)
{
    document.getElementById(element).style.display = "none";
}

function show(element)
{
    document.getElementById(element).style.display = "inline-block";
}

if(navigator.platform.toLowerCase().includes("win"))
{
    hide("graphia-for-macos");
    hide("graphia-for-linux");
}
else if(navigator.platform.toLowerCase().includes("nux"))
{
    hide("graphia-for-windows");
    hide("graphia-for-macos");
}
else if(navigator.platform.toLowerCase().includes("mac"))
{
    hide("graphia-for-windows");
    hide("graphia-for-linux");
}

document.getElementById("show-other-platforms").onclick =
function()
{
    show("graphia-for-windows");
    show("graphia-for-macos");
    show("graphia-for-linux");
};
</script>

Upon starting Graphia for the first time, you will be presented with a short tutorial which runs through the basics of using the software. This can be reactivated at any time from the _Help_ menu. For further information, please consult the [User Guide]({{site.baseurl}}/userguide.html).

<div class="license">
{% include_relative LICENSE %}
</div>

If Graphia proves useful to you, we'd appreciate it if you would consider donating to the project.
{% include_relative donate.html %}
