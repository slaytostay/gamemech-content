---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in site.creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.game.name }} | {{ creator.themes[0].name }} |
{% endfor %}
