---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

{{ site.data.creats[rendi].name }}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in site.data.creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.game }} | {{ creator.theme }} |
{% endfor %}
