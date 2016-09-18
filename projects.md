---
layout: page
title: Projets
description: Mes projets réalisés en en cours
permalink: /projects
---

J'ai rassemblé ici des descriptions de mes principaux projets.
Si vous souhaitez uniquement voir le genre de chose the je fais, consultez plutôt mon [Portfolio web](/web-portfolio).

<ul class="thumbnails-list withtext">
	{% for project in site.projects reversed %}
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
	{% endfor %}
</ul>
