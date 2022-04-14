---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

{{ site.games.quake.name }}

{{ site.themes.educational }}

{% for game in site.games %}
{{ game.name }}
{% endfor %}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in site.creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.games | first }} | {{ creator.themes }} |
{% endfor %}
