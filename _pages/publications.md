---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% if site.author.googlescholar %}
  You can also find my articles on <u><a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% capture written_year %}'None'{% endcapture %}
{% for post in site.publications reversed %}
{% capture year %}{{ post.datename | date: '%Y' }}{% endcapture %}
{% if year != written_year %}
    <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}

  {% include publications.html %}
{% endfor %}
