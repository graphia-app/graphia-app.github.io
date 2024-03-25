---
title: Downloads
---

{% include download-button.html %}

<div class="downloads">
<p><a href="{{site.downloads.release}}">Release Notes</a></p>
<p><a href="{{site.downloads.source}}">Source Code</a></p>
<p><a id="show-other-platforms" href="#">Other Platforms</a></p>
</div>

<script>
document.getElementById("show-other-platforms").onclick =
function()
{
    show("graphia-for-windows");
    show("graphia-for-macos");
    show("graphia-for-linux");
    hide("show-other-platforms");
};
</script>

Upon starting Graphia for the first time, you will be presented with a short tutorial which runs through the basics of using the software. This can be reactivated at any time from the _Help_ menu. For further information, please consult the [User Guide]({{site.url}}/userguide.html).

<div class="license">
{% include_relative LICENSE %}
</div>
