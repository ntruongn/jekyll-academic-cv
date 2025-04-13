---
title: Activities
permalink: /activities/
author_profile: true
---
{% include base_path %}

<h2>Associate Editor</h2>
<ul>
  {% for item in site.data.activities.associate_editor %}
    <li>
      {% if item.journal %}
        {{ item.journal }} ({{ item.years | join: ', ' }})
      {% else %}
        {{ item.conference }} ({{ item.years | join: ', ' }})
      {% endif %}
    </li>
  {% endfor %}
</ul>

<h2>Chair Roles</h2>
<ul>
  {% for chair in site.data.activities.chair_roles %}
    <li>
      {{ chair.role }} - {{ chair.conference }} 
      {% if chair.year %}
        ({{ chair.year }})
      {% else %}
        ({{ chair.years | join: ', ' }})
      {% endif %}
    </li>
  {% endfor %}
</ul>

<h2>Program Committee Member</h2>
<ul>
  {% for item in site.data.activities.pc_member %}
    <li>
      <strong>{{ item.year }}:</strong>
      {{ item.conferences | join: ', ' }}
    </li>
  {% endfor %}
</ul>
