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
<script>
  // http://stackoverflow.com/questions/27765446/directions-to-marker-with-google-maps-api
  // https://wrightshq.com/playground/placing-multiple-markers-on-a-google-map-using-api-3/

  let markers = [
    {
      name: 'Albany',
      coords: {
        lat: 42.6868179,
        lng: -73.8403891
      },
      url: 'https://goo.gl/maps/8M99tphekV52'
    },
    {
      name: 'Troy',
      coords: {
        lat: 42.7338438,
        lng: -73.6872883
      },
      url: 'https://goo.gl/maps/4vTjNvCff6S2'
    },
    {
      name: 'Clifton Park',
      coords: {
        lat: 42.8692993,
        lng: -73.8069645
      },
      url: 'https://goo.gl/maps/g1F1wd1XEi62'
    }
  ];

  function initMap() {
    let map = new google.maps.Map(document.getElementById('capitaloto-map'), {
      zoom: 10,
    });
    let bounds = new google.maps.LatLngBounds();

    // Place markers
    for (let m = 0; m < markers.length; m++) {
      let position = markers[m].coords;
      bounds.extend(position);
      marker = new google.maps.Marker({
        position: position,
        map: map,
        title: markers[m].name
      });

      google.maps.event.addListener(marker, 'click', () => window.location = markers[m].url );
    }

    // Automatically center map, fitting all markers
    map.fitBounds(bounds);
  }
</script>
<script async defer
  src="https://maps.googleapis.com/maps/api/js?key=AIzaSyAfIcDESp0aiadHZ5zoSJTox0TCHyudxmk&callback=initMap">
</script>

Image | Location | Phone | Fax
--- | --- | --- | ---
{% for location in site.data.locations  %}![{{ location.name }}]({{ site.urlimg }}{{ location.image }}) | **{{ location.name }}**<br/>{{ location.address }} | [{{ location.phone }}](tel:{{ location.phone }}) | [{{ location.fax }}](tel:{{ location.fax }})
{% endfor %}

### Hours

Each of our offices is open {{ site.hours }}. Depending on your physician, you may be able to schedule an appointment before or after normal hours.
