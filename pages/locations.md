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
  // https://developers.google.com/maps/documentation/javascript/examples/control-custom

  let bounds;
  let defaultZoom = 11;
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

  function CenterControl(controlDiv, map) {
    // Set CSS for the control border.
    var controlUI = document.createElement('div');
    controlUI.style.backgroundColor = '#fff';
    controlUI.style.border = '2px solid #fff';
    controlUI.style.borderRadius = '3px';
    controlUI.style.boxShadow = '0 2px 6px rgba(0,0,0,.3)';
    controlUI.style.cursor = 'pointer';
    controlUI.style.marginBottom = '22px';
    controlUI.style.textAlign = 'center';
    controlUI.title = 'Click to recenter the map';
    controlDiv.appendChild(controlUI);

    // Set CSS for the control interior.
    var controlText = document.createElement('div');
    controlText.style.color = 'rgb(25,25,25)';
    controlText.style.fontFamily = 'Roboto,Arial,sans-serif';
    controlText.style.fontSize = '12px';
    controlText.style.lineHeight = '24px';
    controlText.style.paddingLeft = '5px';
    controlText.style.paddingRight = '5px';
    controlText.innerHTML = 'Center Map';
    controlUI.appendChild(controlText);

    // Setup the click event listeners: simply set the map to Chicago.
    controlUI.addEventListener('click', function() {
      map.fitBounds(bounds);
      map.setZoom(defaultZoom);
    });
  }

  window.initMap = function() {
    let map = new google.maps.Map(document.getElementById('capitaloto-map'), {
      fullscreenControl: true
    });
    bounds = new google.maps.LatLngBounds();

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

    // Create the DIV to hold the center control and call the CenterControl()
    // constructor passing in this DIV.
    var centerControlDiv = document.createElement('div');
    var centerControl = new CenterControl(centerControlDiv, map);

    centerControlDiv.index = 1;
    map.controls[google.maps.ControlPosition.BOTTOM_CENTER].push(centerControlDiv);

    // Automatically center map, fitting all markers
    map.fitBounds(bounds);
  }
</script>
<script async defer
  src="https://maps.googleapis.com/maps/api/js?key=AIzaSyAfIcDESp0aiadHZ5zoSJTox0TCHyudxmk&callback=initMap">
</script>

Location | Address | Phone | Fax
--- | --- | --- | ---
{% for location in site.data.locations  %}**{{ location.name }}**<br/>![{{ location.name }}]({{ site.urlimg }}{{ location.image }}) | {{ location.address }} | [{{ location.phone }}](tel:{{ location.phone }}) | [{{ location.fax }}](tel:{{ location.fax }})
{% endfor %}

### Hours

Each of our offices is open {{ site.hours }}. Depending on your physician, you may be able to schedule an appointment before or after normal hours.
