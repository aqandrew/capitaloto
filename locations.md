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

We have 3 offices dedicated to serving patients throughout and outside the Capital Region with the utmost care and convenience.
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

### Hours

Location | Hours | Phone | Fax
--- | --- | --- | ---
**Albany**<br/>6 Executive Park Drive<br/>Entrance C<br/>Albany, NY 12203 | TODO | [(518)482-9111](tel:5184829111) | [(518)482-6142](tel:5184826142)
**Troy**<br/>2001 5th Avenue<br/>Troy, NY 12180 | TODO | [(518)274-4110](tel:5182744110) | [(518)272-5147](tel:5182725147)
**Clifton Park**<br/>963 Route 146<br/>Clifton Park, NY 12065 | TODO | [(518)383-0065](tel:5183830065) | [(518)383-2239](tel:5183832239)
