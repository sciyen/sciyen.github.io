---
layout: page
title: Projects
permalink: /projects/
---

<h1>Projects</h1>

{% for project in site.data.projects %}
<div>
    {% if project.url %}
    <h3><a href="{{project.url}}">{{ project.name }}</a></h3>
    {% else %}
    <h3>{{ project.name }}</h3>
    {% endif %}
    <div>
        <img src="{{project.cover-photo}}" alt="{{ project.name }}">
    </div>
    <div>{{ project.team }}</div>
    <div>
        {% if project.tags %}
        <div>
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
    </div>
</div>
{% endfor %}
