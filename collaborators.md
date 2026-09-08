---
layout: default
title: Collaborators
---

<section class="collaborators-intro">
  <h2>Collaborators</h2>
  <p class="intro-text">
    Everyone who has submitted a work to WriterSkill. Click a name to read
    their bionote and browse their works.
  </p>
</section>

{% assign pennames = site.posts | map: "penname" | uniq | sort_natural %}

<section class="collaborator-list">
  {% for penname in pennames %}
    {% assign slug = penname | slugify %}
    <a class="collaborator-card" href="{{ "/collaborators/" | append: slug | append: "/" | relative_url }}">
      {{ penname }}
    </a>
  {% endfor %}
</section>
