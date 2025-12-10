+++
title="Portfolio"
+++

This is a basic rich page with colocated assets.


Using Zola's <a href="https://www.getzola.org/documentation/content/image-processing/">image-processing tools</a>
```
<div>
{% for asset in page.assets -%}
  {%- if asset is matching("[.](jpg|png)$") -%}
    {% set image = resize_image(path=asset, width=240, height=180) %}
    <a href="{{ get_url(path=asset) }}" target="_blank">
      <img src="{{ image.url }}" />
    </a>
  {%- endif %}
{%- endfor %}
</div>
```