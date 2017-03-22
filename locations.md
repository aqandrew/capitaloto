---
layout: page
title: Locations & Directions
permalink: /locations/
---

<style>
  #capitaloto-map {
    height: 60vh;
  }
</style>

Click each marker on the map below for directions to one of our locations.

<div id="capitaloto-map"></div>
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
      center: markers[0].coords
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

There's one for:
- Albany
- Troy
- Latham
