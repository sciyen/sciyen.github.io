---
layout: page
title: Activities
permalink: /activities/
custom_js: true
---

<div class="collection-container">
    {% for event in site.data.activities %}
    <h3>{{ event.title }}</h3>
    <div>
        <!-- Time -->
        {% if event.time %}
        <div>{{ event.time }}</div>
        {% endif %}
        {% if event.location %}
        <div>{{ event.location }}</div>
        {% endif %}
        <!-- Photos -->
        {% if event.photo-dir %}
        <ul class="photo-gallery">
        {% for image in site.static_files %}
            {% if image.path contains event.photo-dir %}
                {% assign thumb_url = image.path | remove: image.name | append: 'thumbnails/' | append: image.name  | remove: image.extname | append: '_50w' | append: image.extname %}
                {% unless image.path contains 'thumbnails' %}
                {% if thumb_url %}
                    <li data-thumb="{{ thumb_url }}">
                {% endif %}
                <img src="{{ image.path }}" alt="" loading="lazy"/>
                </li>
                {% endunless %}
            {% endif %}
        {% endfor %}
        </ul>
        {% endif %}
        <!-- Description -->
        {% if event.description %}
        <span>{{ event.description }}</span>
        {% endif %}
    </div>
    {% endfor %}
</div>

<script>
    // https://github.com/sachinchoolur/lightslider
    $(document).ready(function() {
        $(".photo-gallery").lightSlider({
            gallery: true,
            item: 1,
            loop: true,
            thumbItem: 9,
            slideMargin: 0,
            enableDrag: false,
            currentPagerPosition: 'left',
        });
    });
</script>