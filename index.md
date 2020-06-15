---
layout: page
title: Discography
description: Discography of Julia Koshkina
keywords: [koshkamoroshka,Julia Koshkina,discography,кошка морошка,Юля Кошкина,дискография]
ogtitle: Discography
ogdescription: Listen to Julia's music on Spotify, Apple Music and Google Play
ogimage: latest.jpg
---

{% for album in site.data.albums %}

### {{ album.title }}
_{{ album.date | date: "%-d %B %Y" }}_

{% for track in album.tracks -%}
{{ forloop.index }}. {{ track.title }} `{{ track.length }}`
{% for tags in track.links -%}
[]({{ tags[1] }}){:target="_blank"} 
{% endfor -%}
{% endfor %}
{% for tags in album.links -%}
[{{ tags[0] }}]({{ tags[1] }}){:target="_blank"}
{% endfor -%}
{% endfor %}

# Singles
{% for single in site.data.singles %}
### {{ single.title }} `{{ single.length }}` []({{ single.links.GitHub }}){:target="_blank"}
_{{ single.date | date: "%-d %B %Y" }}_

{% for tags in single.links -%}
{% if tags[0] != 'GitHub' %}[{{ tags[0] }}]({{ tags[1] }}){:target="_blank"} {% endif %}
{% endfor -%}
{% endfor %}
