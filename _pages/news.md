---
title: News
permalink: /news/
author_profile: true
---
{% include base_path %}
<ul style="list-style-type: none; padding-left: 0;">
  {% assign sorted_news = site.data.news.news | sort: "date" | reverse %}
  {% for item in sorted_news %}
    <li>
      <strong>{{ item.date }}</strong> -
      {{ item.title }}
      {% if item.venue %}
        at <em>{{ item.venue }}</em>
      {% endif %}
      {% if item.award %}
        ({{ item.award }})
      {% endif %}
      {% if item.links %}
        {% for link in item.links %}
          {% for key in link %}
            (<a href="{{ link[key] }}" target="_blank">{{ key }}</a>)
          {% endfor %}
        {% endfor %}
      {% endif %}
      {% if item.locations %}
        at {{ item.locations | join: ', ' }}
      {% endif %}
    </li>
  {% endfor %}
</ul>

