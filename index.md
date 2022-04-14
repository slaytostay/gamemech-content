---
title: "Creators"
layout: public
permalink: /
---

{{ site.description }}

## Creators
{% assign creators = "" | split: ',' %}
{% for creator_hash in site.data.creators %}
{% assign creator = creator_hash[1] %}
{% assign creators = creators | push: creator %}
{% endfor %}
{% assign creators = creators | sort_natural: "name" %}

| Creator | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.games | first }} | {{ creator.themes | first }} |
{% endfor %}
