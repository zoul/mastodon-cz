---
layout: default
---

# Český průvodce Mastodonem

Mastodon je sociální síť podobná Twitteru, ale nejsou na ní reklamy a můžete si sami lépe vybrat,
co chcete vidět.

Dalším podstatným rozdílem proti Twitteru je decentralizace – Mastodon se skládá ze stovek navzájem
propojených serverů neboli _instancí_. Funguje to podobně jako e-mail – můžete si založit účet na
libovolném serveru (případně spustit vlastní) a komunikovat s uživateli z jiných serverů. Výhodou
je, že si můžete vybrat server, jehož pravidla vám vyhovují, a nemusíte se řídit rozmary miliardářů,
protože Mastodon nemá žádného centrálního vlastníka.

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

Následující servery můžeme doporučit, protože se zavázaly k dodržování některých
[praktických pravidel](https://joinmastodon.org/covenant), například základnímu
moderování obsahu, dennímu zálohování nebo dlouhodobé udržitelnosti serveru.

{% for instance in featuredInstances %}

<div class="instance">
  <h3><a href="{{instance.url}}">{{instance.name}}</a></h3>
  <p>{{instance.description}}</p>
</div>

{% endfor %}

### Další servery

Na těchto serverech nemusí být nic špatného, ale nemusí například vůbec moderovat
obsah, mohou ze dne na den ukončit provoz a podobně.

{% for instance in otherInstances %}

<div class="instance">
  <h3><a href="{{instance.url}}">{{instance.name}}</a></h3>
  <p>{{instance.description}}</p>
</div>

{% endfor %}

## Často kladené otázky

**Kdo to platí?**

Mastodon jako takový je něco jako internet – nemá jednoho majitele, nemá ho kdo platit.
Software, na kterém běží, je [open source](https://github.com/mastodon/mastodon). Provoz
serverů něco stojí, jejich byznys model je různý – zatím jde nejčastěji o dobrovolnickou
činnost, takže se nebojte na svém serveru zeptat, jestli můžete někam přispět na provoz.

**Co je fediverse?**

Podobně jako je Mastodon decentralizovaná alternativa Twitteru, existují decentralizované
alternativy dalších centralizovaných služeb, například [Pixelfed](https://pixelfed.org) je
alternativa Instagramu a [PeerTube](https://joinpeertube.org) je alternativa YouTube. Tyto
služby používají stejný protokol [ActivityPub](https://en.wikipedia.org/wiki/ActivityPub)
(stručně řečeno „mluví podobným jazykem“), takže jsou navzájem do jisté míry kompatibilní
a tvoří velkou síť, které se říká fediverse (_federated universe_).

## Odkazy

{% for post in site.data.posts %}

<div class="post">
  <h3><a href="{{post.url}}">{{post.title}}</a></h3>
  <p>{{post.description}}</p>
</div>

{% endfor %}
