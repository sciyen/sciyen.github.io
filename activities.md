---
layout: page
title: Activities
permalink: /activities/
---

<div class="collection-container">
    {% for event in site.data.activities %}
    <h3>{{ event.title }}</h3>
    <div>
        <!-- Time -->
        {% if event.time %}
        <div>{{ event.time }}</div>
        {% endif %}
        <!-- Cover -->
        {% if event.cover-photo %}
        <img src="{{ event.cover-photo }}" alt="{{ event.title }}" loading="lazy">
        {% endif %}
        <!-- Photos -->
        {% if event.photos %}
        <div class="photo-gallery">
            {% for photo-url in event.photos %}
            <img src="{{ photo-url }}" alt="" loading="lazy">
            {% endfor %}
        </div>
        {% endif %}
        <!-- Description -->
        {% if event.description %}
        <span>{{ event.description }}</span>
        {% endif %}
    </div>
    {% endfor %}
</div>