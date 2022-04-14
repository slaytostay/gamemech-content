---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

{{ site.games.quake }}

{{ site.themes.educational }}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in site.creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.games }} | {{ creator.themes }} |
{% endfor %}
