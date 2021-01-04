---
layout: content
title: Show Dates
---

<ul class="news">
    {% for show in site.data.shows %}
    <li>
        <div class="date"><p><span>{{ show.start | date_to_long_string }}</span></p></div>
        <h1>{{ show.name | title }}</h1>
        <p>&nbsp;</p>
        <p><b>{{ show.name }}</b> will take place between <b>{{ show.start | date_to_long_string }}</b> and <b>{{ show.end | date_to_long_string }}</b>. This show will take place in: <b>{{ show.location }}</b>.</p>
        {% if show.address %}
        <p>The full address for this event is: {{ show.address }}</p>
        {% endif %}
        {% if show.description %}{{ show.description | safe }}{% endif %}
        {% if show.urls.size > 0 %}
        <p>The following links provide relevant info for the event.</p>
        {% for url in  show.urls %}
            <p>Click <a href="{{ url.url }}">here for the {{ url.name }}</a>.</p>
        {% endfor %}
        {% endif %}
        {% if show.latitude %}
        {% if show.longitude %}
        <p>
            <iframe width="300" height="300"
                    src="https://maps.google.com/maps?q={{ show.latitude }},{{ show.longitude }}{%raw%}&{%endraw%}hl=es;z=14{%raw%}&{%endraw%}amp;output=embed"></iframe>
        </p>
        {% endif %}
        {% endif %}
    </li>
    {% endfor %}
</ul>

