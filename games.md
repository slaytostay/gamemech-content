---
title: Games
layout: public
permalink: /games/
---

{{ site.description }}

## Games

{% assign games = "Oldschool RuneScape" | split: ',' %}
{% for creator_hash in site.data.creators %}
  {% assign creator = creator_hash[1] %}
  {% for creator_game in creator.games %}
    {% assign add_game = 1 %}
    {% for game in games %}
      {% if game contains creator_game %}
        {% assign add_game = 0 %}
        {% break %}
      {% endif %}
    {% endfor %}
    {% if add_game == 1 %}
      {% assign games = games | push: creator_game %}
    {% endif %}
  {% endfor %}
{% endfor %}

{% assign games = games | sort_natural %}
{% for game in games %}

{% assign creators = "" | split: ',' %}
{% for creator_hash in site.data.creators %}
  {% assign creator = creator_hash[1] %}
  {% assign add_creator = 0 %}
  {% for creator_game in creator.games %}
    {% if creator_game contains game %}
      {% assign add_creator = 1 %}
      {% break %}
    {% endif %}
  {% endfor %}
  {% if add_creator == 1 %}
    {% assign creators = creators | push: creator %}
  {% endif %}
{% endfor %}
{% assign creators = creators | sort_natural: "name" %}

### {{ game }}

| Creator | Main Game | Main Theme |
| --- | --- | --- |
{% for creator in creators %}| [{{ creator.name }}]({{ creator.channel }}) | {{ creator.games | first }} | {{ creator.themes | first }} |
{% endfor %}

{% endfor %}

