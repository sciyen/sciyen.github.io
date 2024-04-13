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
        <!-- Photos -->
        {% if event.photo-dir %}
        <ul class="photo-gallery">
        {% for image in site.static_files %}
            {% if image.path contains event.photo-dir %}
                <li data-thumb="{{ image.path }}">
                <img src="{{ image.path }}" alt="" loading="lazy"/>
                </li>
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