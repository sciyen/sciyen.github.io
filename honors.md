---
layout: page
title: Honors
permalink: /honors/
---

<h1>Awards</h1>

<ul class="timeline">
{% for item in site.data.awards %}
    <li>
        <div class="direction-r">
            <div class="flag-wrapper">
                <span class="flag">{{ item.name }}</span>
                <span class="time-wrapper">{{ item.time }}</span>
            </div>
            {% if item.price %}
            <div class="desc">
                <span>{{ item.title }}</span>
                <span>{{ item.price }}</span>
            </div>
            {% endif %}
            <div class="note">
                <span>{{ item.story }}</span>
                <!-- <span>{{ item.content }}</span> -->
            </div>
        </div>
    </li>
{% endfor %}
</ul>


<h1>News</h1>

<div class="story-container">
{% for item in site.data.news %}
    <div class="story-item">
        {% if item.youtube-iframe %}
            <iframe class="content-cover" width="400" height="300" src="{{ item.youtube-iframe }}" title="{{ item.url }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        {% elsif item.preview-url %}
            <a href="{{ item.url }}" target="_blank">
                <img class="content-cover" src="{{item.preview-url}}">
            </a>
        {% else %}
            <div class="content-cover"><a href="{{ item.url }}" target="_blank"></a></div>
        {% endif %}
        <div class="desc">
            <h3><a href="{{ item.url }}" target="_blank">{{ item.title }}</a></h3>
            <div class="meta">
                <p>{{ item.publisher }}</p>
                <p>{{ item.time }}</p>
            </div>
        </div>
    </div>
{% endfor %}
</div>