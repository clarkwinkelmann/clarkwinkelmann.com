---
layout: page
title: Open-source
permalink: /open-source
---

My open-source projects and contributions.

<div class="opensource-showcase">
	{% for category in site.data.opensource %}
	<div class="category">
        <h2>{{ category.category }}</h2>
        <div class="description">{{ category.description | markdownify }}</div>
        <div class="projects">
            {% for project in category.projects %}
            <div class="project">
                {% if project.image %}
                <div class="thumbnail" style="background-image: url({{ project.image }})"></div>
                {% else %}
                <div class="thumbnail"><span class="fa fa-code"></span></div>
                {% endif %}
                <h3>{{ project.title }}</h3>
                <div class="description">{{ project.description }}</div>
                {% if project.more %}
                <a class="button" href="{{ project.more }}">Learn more</a>
                {% endif %}
                {% if project.github %}
                {% capture repo %}{{ project.github | replace:'https://github.com/clarkwinkelmann/','' | replace:'https://github.com/','' }}{% endcapture %}
                <a class="button" href="{{ project.github }}"><span class="fa fa-github"></span> {{ repo }}</a>
                {% endif %}
            </div>
            {% endfor %}
            {% if category.more_to_come %}
            <div class="project more">
                <div class="thumbnail"><span class="fa fa-plus"></span></div>
                <h3>More to come</h3>
            </div>
            {% endif %}
        </div>
    </div>
    {% endfor %}
</div>
