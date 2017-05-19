---
layout: page-fullwidth
title: Locations & Directions
permalink: /locations/
---

<style>
  #capitaloto-map {
    height: 60vh;
  }
</style>

We have 3 offices dedicated to serving patients throughout and outside the Capital Region with the utmost care and convenience.
Click each marker on the map below for directions to one of our locations.

**Note**: The interactive map may not display in Internet Explorer. You can also click the images in the table below for directions.

<div id="capitaloto-map" class="b15"></div>

### Contact

Location | Image | Address | Phone | Fax
--- | --- | --- | --- | ---
{% for location in site.data.locations  %}**{{ location.name }}** | [![{{ location.name }}]({{ site.urlimg }}{{ location.image }})]({{ location.url }}) | {{ location.address }} | [{{ location.phone }}](tel:{{ location.phone }}) | [{{ location.fax }}](tel:{{ location.fax }})
{% endfor %}

### Hours

Each of our offices is open {{ site.hours }}. Depending on your physician, you may be able to schedule an appointment before normal hours.
