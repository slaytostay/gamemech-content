---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

{% assign crtr = site.data.creators["rendi"] %}
{{ crtr.name }}

## Creators

| Name | Main Game | Main Theme |
| --- | --- | --- |
{% for creator_hash in site.data.creators %}{% assign creator = creator_hash[0] %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.game }} | {{ creator.theme }} |
{% endfor %}
