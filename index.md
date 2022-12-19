---
layout: default
---

# Mastodon.cz

(Úvodní text o tom, co Mastodon je a jak funguje)

## České servery

{% for instance in site.data.instances %}

<div class="instance">
  <h3><a href="{{instance.url}}">{{instance.name}}</a></h3>
  <p>{{instance.description}}</p>
</div>

{% endfor %}

## Často kladené otázky

TBD

## Odkazy

{% for post in site.data.posts %}

<div class="post">
  <h3><a href="{{post.url}}">{{post.title}}</a></h3>
  <p>{{post.description}}</p>
</div>

{% endfor %}
