---
layout: page
title: Presentations
permalink: /presentations/
---

# Project Presentations

This page contains presentations from BUGATTI project meetings, workshops, and events.

## How to Contribute

Project partners can add presentations by:
1. Adding PDF files to the `assets/presentations/` directory
2. Creating a new entry in the `_presentations` collection with metadata
3. Submitting a pull request or contacting the project coordinator

---

## Available Presentations

{% if site.presentations.size > 0 %}
<div class="presentations-list">
{% for presentation in site.presentations reversed %}
  <div class="presentation-item">
    <h3>{{ presentation.title }}</h3>
    <p class="meta">
      <strong>Date:</strong> {{ presentation.date | date: "%B %d, %Y" }}<br>
      <strong>Speaker:</strong> {{ presentation.speaker }}<br>
      {% if presentation.event %}
      <strong>Event:</strong> {{ presentation.event }}<br>
      {% endif %}
    </p>
    {% if presentation.description %}
    <p>{{ presentation.description }}</p>
    {% endif %}
    {% if presentation.slides %}
    <p><a href="{{ presentation.slides | relative_url }}" class="btn">Download Slides (PDF)</a></p>
    {% endif %}
  </div>
  <hr>
{% endfor %}
</div>
{% else %}
<p><em>No presentations have been published yet. Check back soon for updates from our meetings and events.</em></p>
{% endif %}

---

## Upcoming Presentations

Check the [calendar page](/bugatti/calendar) for information about upcoming meetings and events.

<style>
.presentation-item {
  margin: 2em 0;
}
.presentation-item h3 {
  margin-bottom: 0.5em;
  color: #2a7ae2;
}
.meta {
  color: #666;
  font-size: 0.9em;
}
.btn {
  display: inline-block;
  padding: 8px 16px;
  background: #2a7ae2;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  margin-top: 8px;
}
.btn:hover {
  background: #1e5bb8;
}
</style>
