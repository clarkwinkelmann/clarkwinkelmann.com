---
layout: page
title: Portfolio web
description: Mes réalisations web
permalink: /web-portfolio
---

Vous trouverez ci-dessous mes dernières créations web, triées plus ou moins de la plus récente à la plus ancienne.

N'hésitez pas à cliquer sur "Visiter le site" pour aller jeter un coup d'oeil pour de vrai !

Envie de créer votre prochain site avec moi ? Il suffit de me contacter !

<div class="websites-showcase">
    {% for website in site.data.websites %}
    <div class="website">
        <div class="preview">
            <div class="desktop">
                <div class="browser">
                    <div class="browser-gui">
                        <div class="browser-window">
                            <div class="browser-tabs">
                                <div class="browser-tab">{{ website.title }}</div>
                                <div class="new-tab"></div>
                            </div>
                            <div class="browser-buttons">
                                <span><i class="fas fa-expand" aria-hidden="true"></i></span>
                                <span><i class="fas fa-times" aria-hidden="true"></i></span>
                            </div>
                        </div>
                        <div class="browser-bar">
                            <i class="fas fa-arrow-left" aria-hidden="true"></i>
                            <i class="fas fa-arrow-right" aria-hidden="true"></i>
                            <i class="fas fa-redo" aria-hidden="true"></i>
                            <div class="browser-address">
                                <span class="browser-url">{{ website.url | replace:'https://','<span class="https">https</span>://' }}</span>
                                <i class="far fa-star" aria-hidden="true"></i>
                            </div>
                            <i class="fas fa-bars" aria-hidden="true"></i>
                        </div>
                    </div>
                    <div class="browser-page" style="background-image: url({{ website.screenshot }})"></div>
                </div>
            </div>
            {% if website.screenshot_mobile %}
            <div class="mobile">
                <div class="browser">
                    <div class="browser-gui">
                        <div class="phone-bar">
                            <i class="fas fa-volume-off" aria-hidden="true"></i>
                            <i class="fas fa-wifi" aria-hidden="true"></i>
                            <i class="fas fa-battery-three-quarters" aria-hidden="true"></i>
                            <span>12:42</span>
                        </div>
                        <div class="browser-bar">
                            <div class="browser-address">
                                <span class="browser-url">{{ website.url | replace:'https://','<span class="https">https</span>://' }}</span>
                            </div>
                            <i class="fas fa-bars" aria-hidden="true"></i>
                        </div>
                    </div>
                    <div class="browser-page" style="background-image: url({{ website.screenshot_mobile }})"></div>
                </div>
            </div>
            {% endif %}
        </div>
        <div class="about">
            <div class="about-text">
                <h2>{{ website.title }}</h2>
                {% if website.description %}
                <p>{{ website.description }}</p>
                {% endif %}
            </div>
            <ul class="about-links">
                {% if website.archive_url %}
                <li><a href="{{ website.archive_url }}"><i class="fas fa-mouse-pointer" aria-hidden="true"></i> Archive du site</a></li>
                {% else %}
                <li><a href="{{ website.url }}"><i class="fas fa-mouse-pointer" aria-hidden="true"></i> Visiter le site</a></li>
                {% endif %}
                {% if website.project_page %}
                <li><a href="{{ website.project_page }}"><i class="fas fa-info-circle" aria-hidden="true"></i> Page du projet</a></li>
                {% endif %}
                {% if website.source_page %}
                <li><a href="{{ website.source_page }}"><i class="fas fa-code-branch" aria-hidden="true"></i> Code source</a></li>
                {% endif %}
            </ul>
        </div>
    </div>
    {% endfor %}
</div>
