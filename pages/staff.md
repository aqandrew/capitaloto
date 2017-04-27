---
layout: page-fullwidth
title: Providers and Staff
permalink: /staff/
nav_order: 0
---
## Medical Providers

<table>
  <tbody>
  {% for provider in site.data.staff.medical_providers %}
  <tr>
    <td>
      <h3 class="nomargin">
        {{ provider.name }}
      </h3>
      <img src="{{ provider.image }}" alt="{{ provider.name }}">
      <h5 class="nomargin">
        {{ provider.practicing_since }}
      </h5>
      <h5 class="nomargin">
        Specialty: {{ provider.specialty }}
      </h5>
    </td>
    <td>
      {% for position in provider.positions %}
        <h5>{{ position.name }}</h5>
        <h6>{{ position.location }}</h6>
      {% endfor %}
    </td>
  </tr>
  {% endfor %}
  </tbody>
</table>

## Audiologists

{% for audiologist in site.data.staff.audiologists %}
- {{ audiologist.name }}
{% endfor %}
