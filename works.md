---
layout: default
title: Works
---

<section class="events-intro">
  <h2>Works</h2>
  <p class="intro-text">
    Browse submitted works by event. Pick an event below to see everything
    that was submitted for it.
  </p>
</section>

<section class="event-list">
  {% for event in site.data.events %}
    {% assign event_posts = site.posts | where: "event", event.slug %}
    <article class="event-card">
      <h3><a href="{{ "/works/" | append: event.slug | append: "/" | relative_url }}">{{ event.name }}</a></h3>
      <p class="meta">
        {{ event_posts.size }} work{% unless event_posts.size == 1 %}s{% endunless %} submitted
      </p>
      <a class="read-more" href="{{ "/works/" | append: event.slug | append: "/" | relative_url }}">View works →</a>
    </article>
  {% endfor %}
</section>
