---
layout: default
---

# Mastodon.cz

(Úvodní text o tom, co Mastodon je a jak funguje)

## České servery

{% for instance in site.data.instances %}

<div class="instance">
  <h3>{{instance.name}}</h3>
  <p>{{instance.description}}</p>
</div>

{% endfor %}

## Často kladené otázky

TBD

## Odkazy

TBD
