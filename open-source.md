---
layout: page
title: Open-source
permalink: /open-source
---

Some of my notable open-source projects and contributions.
Check out my [GitHub profile](https://github.com/clarkwinkelmann).

<div class="opensource-showcase">
	{% for category in site.data.opensource %}
	<div class="category">
        <h2>{{ category.category }}</h2>
        <div class="description">{{ category.description | markdownify }}</div>
        <div class="projects row">
            {% for project in category.projects %}
            <div class="project col-md-3">
                {% if project.image %}
                <div class="thumbnail has-image" style="background-image: url({{ project.image }})"></div>
                {% else %}
                <div class="thumbnail has-icon"><span class="fas fa-code"></span></div>
                {% endif %}
                <h3>{{ project.title }}</h3>
                <div class="description">{{ project.description }}</div>
                {% if project.more %}
                <a class="button" href="{{ project.more }}">Learn more</a>
                {% endif %}
                {% if project.github %}
                {% capture repo %}{{ project.github | replace:'https://github.com/clarkwinkelmann/','' | replace:'https://github.com/','' }}{% endcapture %}
                <a class="button" href="{{ project.github }}"><span class="fab fa-github"></span> {{ repo }}</a>
                {% endif %}
            </div>
            {% cycle category.category: '', '', '', '</div><div class="projects row">' %}
            {% endfor %}
            {% if category.more_to_come %}
            <div class="project more col-md-3">
                <div class="thumbnail has-icon"><span class="fas fa-plus"></span></div>
                <h3>More to come</h3>
            </div>
            {% endif %}
        </div>
    </div>
    {% endfor %}
</div>
