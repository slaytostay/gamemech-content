---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in site.data.creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.games | first }} | {{ creator.themes }} |
{% endfor %}
