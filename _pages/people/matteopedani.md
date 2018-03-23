---
#title: "Matteo Pedani aa"
sitemap: true
permalink: /matteopedani/
author: "Matteo Pedani" 
layout: archive
author_profile: true
---
## Musics and events {{ author.name }}

 
{% assign author = site.data.authors[page.author] %}
<a rel="author"
  href="https://soundmotion.net/{{ author.soundmotion }}"
  title="{{ author.name }}">
    {{ author.name }}
</a>

<a rel="twit"
  href="https://twitter.com/{{ author.twitter }}"
  title="twitter {{ author.name }}">
    twitter {{ author.name }}
</a>

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
  {% unless collection.output == false or collection.label == "posts" %}
    {% capture label %}{{ collection.label }}{% endcapture %}
    {% if label != written_label %}
      <h2 id="{{ label | slugify }}" class="archive__subtitle">{{ label }}</h2>
      {% capture written_label %}{{ label }}{% endcapture %}
    {% endif %}
  {% endunless %}
  {% for post in collection.docs %}
    {% unless collection.output == false or collection.label == "posts" %}
      {% include archive-single.html %}
    {% endunless %}
  {% endfor %}
{% endfor %}
