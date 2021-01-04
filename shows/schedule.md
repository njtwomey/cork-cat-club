---
layout: content
title: Show Dates
---

<ul class="news">
    {% for show in site.data.shows %}
    <li>
        <div class="date"><p><span>{{ show.start | date_to_long_string }}</span></p></div>
        <h1>{{ show.name | capitalize }}</h1>
        <p>&nbsp;</p>
<p>This {{ show.name }} will take place on <b>{{ show.start | date_to_long_string }}</b> at <b>{{ show.location }}</b> between <b>{{ show.start | date: "%r" }}</b> and <b>{{ show.end | date: "%r" }}</b>.</p>
        {% if show.address %}
        <p>The full address for this event is: {{ show.address }}</p>
        {% endif %}
        {% if show.urls.size > 0 %}
        <p>The following links provide relevant info for the event.</p>
        {% for url in  show.urls %}
            <p>Click <a href="{{ url.url }}">here for the {{ url.name }}</a>.</p>
        {% endfor %}
        {% endif %}
        <p>
            <iframe width="300" height="300"
                    src="https://maps.google.com/maps?q={{ show.latitude }},{{ show.longitude }}{%raw%}&{%endraw%}hl=es;z=14{%raw%}&{%endraw%}amp;output=embed"></iframe>
        </p>
    </li>
    {% endfor %}
</ul>

