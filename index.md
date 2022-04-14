---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

{% assign crtr = site.data.creators[rendi] %}
{{ crtr.name }}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in site.data.creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.game }} | {{ creator.theme }} |
{% endfor %}
