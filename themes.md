---
title: Themes
layout: public
permalink: /themes/
---

{{ site.description }}

## Games

{% assign themes = "Educational" | split: ',' %}
{% for creator_hash in site.data.creators %}
  {% assign creator = creator_hash[1] %}
  {% for creator_theme in creator.themes %}
    {% assign add_theme = 1 %}
    {% for theme in themes %}
      {% if theme contains creator_theme %}
        {% assign add_theme = 0 %}
        {% break %}
      {% endif %}
    {% endfor %}
    {% if add_theme == 1 %}
      {% assign themes = themes | push: creator_theme %}
    {% endif %}
  {% endfor %}
{% endfor %}

{% assign themes = themes | sort_natural %}
{% for theme in themes %}

{% assign creators = "" | split: ',' %}
{% for creator_hash in site.data.creators %}
  {% assign creator = creator_hash[1] %}
  {% assign add_creator = 0 %}
  {% for creator_theme in creator.themes %}
    {% if creator_theme contains theme %}
      {% assign add_creator = 1 %}
      {% break %}
    {% endif %}
  {% endfor %}
  {% if add_creator == 1 %}
    {% assign creators = creators | push: creator %}
  {% endif %}
{% endfor %}
{% assign creators = creators | sort_natural: "name" %}

### {{ theme }}

| Creator | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.games | first }} | {{ creator.themes | first }} |
{% endfor %}

{% endfor %}

