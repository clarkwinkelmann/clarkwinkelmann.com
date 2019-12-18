---
layout: page
title: Projets
description: Mes projets réalisés en en cours
permalink: /projects
---

Vous trouvez ici les anciennes pages de présentation de certains de mes projets qui n'ont pas encore pu être placés dans une nouvelle zone du site.
Si vous souhaitez uniquement voir le genre de chose the je fais, consultez plutôt mon [Portfolio web](/web-portfolio).

<div class="row">
  {% for project in site.projects reversed %}
    <div class="col-md-6">
      <a href=".{{ project.url }}" class="old-project-thumbnail-item">
        {% if project.cover %}
            <div class="image"><img src="{{ project.cover }}" alt="Illustration pour le projet {{ project.title }}"></div>
        {% endif %}
        <div class="text">
            <div class="title">{{ project.title }}</div>
            <div class="desc">{{ project.description }}</div>
        </div>
        <div class="date">{{ project.date | date: "%B %Y" }}</div>
      </a>
    </div>
    {% cycle '', '</div><div class="row">' %}
  {% endfor %}
</div>
