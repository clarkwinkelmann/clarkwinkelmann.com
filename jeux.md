---
layout: page
title: Jeux
description: Différents jeux que j'ai réalisés
permalink: /jeux
---

<p>Voici différents jeux que j'ai créés. Certains sont des applications natives, d'autres se jouent en ligne. Certains sont des travaux scolaire, d'autres de loisirs.</p>

<ul class="thumbnails-list withtext">
	{% for project in site.projects reversed %}
		{% if project.categories contains "game" %}
			<li><a href=".{{ project.url }}" class="thumbnail-item">
				{% if project.cover %}
					<div class="image"><img src="{{ project.cover }}" alt="Illustration pour le projet {{ project.title }}"></div>
				{% endif %}
				<div class="text">
					<div class="title">{{ project.title }}</div>
					<div class="desc">{{ project.description }}</div>
				</div>
				<div class="date">{{ project.date | date: "%B %Y" }}</div>
			</a></li>
		{% endif %}
	{% endfor %}
</ul>