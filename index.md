---
layout: default
---

# Český průvodce Mastodonem

_(Úvodní text o tom, co Mastodon je a jak funguje)_

## České servery

{% assign featuredInstances = site.array %}
{% assign otherInstances = site.array %}

{% assign instanceCount = site.data.instances | size %}
{% assign randomizedInstances = site.data.instances | sample: instanceCount %}

{% for instance in randomizedInstances %}
{% if instance.featured %}
{% assign featuredInstances = featuredInstances | push: instance %}
{% else %}
{% assign otherInstances = otherInstances | push: instance %}
{% endif %}
{% endfor %}

### Doporučujeme

_(Úvodní text o tom, proč je doporučujeme)_

{% for instance in featuredInstances %}

<div class="instance">
  <h3><a href="{{instance.url}}">{{instance.name}}</a></h3>
  <p>{{instance.description}}</p>
</div>

{% endfor %}

### Další servery

{% for instance in otherInstances %}

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
