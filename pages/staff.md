---
layout: page
title: Providers and Staff
permalink: /staff/
nav_order: 0
---

TODO This is the page where all of the doctors will be listed.

## Medical Providers

{% for provider in site.data.staff.medical_providers %}
- {{ provider.name }}
{% endfor %}

## Audiologists

{% for audiologist in site.data.staff.audiologists %}
- {{ audiologist.name }}
{% endfor %}
