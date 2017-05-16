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

<div id="capitaloto-map" class="b15"></div>
<script async defer
  src="https://maps.googleapis.com/maps/api/js?key=AIzaSyAfIcDESp0aiadHZ5zoSJTox0TCHyudxmk&callback=initMap">
</script>
<script src="{{ site.url }}{{ site.baseurl }}/assets/js/capitalotoMap.js"></script>

Location | Address | Phone | Fax
--- | --- | --- | ---
{% for location in site.data.locations  %}**{{ location.name }}**<br/>![{{ location.name }}]({{ site.urlimg }}{{ location.image }}) | {{ location.address }} | [{{ location.phone }}](tel:{{ location.phone }}) | [{{ location.fax }}](tel:{{ location.fax }})
{% endfor %}

### Hours

Each of our offices is open {{ site.hours }}. Depending on your physician, you may be able to schedule an appointment before normal hours.
