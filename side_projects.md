---
layout: page
title: Projects
permalink: /projects/
---

<div class="collection-container">
    {% for project in site.data.projects %}
    <h3>{{ project.name }}</h3>
    <div class="collection-item">
        <!-- <div> -->
            <img src="{{ project.cover-photo }}" alt="{{ project.name }}">
        <!-- </div> -->
        <div class="flag">
            {% if project.time %}
            <div>{{ project.time }}</div>
            {% endif %}
            {% if project.team %}
            <div>{{ project.team }}</div>
            {% endif %}
        </div>
        <div>
            {% if project.tags %}
            <div class="tags-container">
                {% for tag in project.tags %}
                <span>{{ tag }}</span>
                {% endfor %}
            </div>
            {% endif %}
            {% if site.tags %}
            <div>
            <p>{{ project.description }}</p>
            </div>
            {% endif %}
            {% if project.url %}
            <span class="link">
                <a href="{{ project.url }}" target="_blank">
                    <span class="fa fa-code"></span>
                </a>
            </span>
            {% endif %}
            {% if project.video %}
            <span class="link">
                <a href="{{ project.video }}" target="_blank">
                    <span class="fa fa-play"></span>
                </a>
            </span>
            {% endif %}
        </div>
    </div>
    {% endfor %}
</div>