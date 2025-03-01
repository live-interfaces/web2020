---
layout: page
title: Trondheim
---

<script src='https://api.tiles.mapbox.com/mapbox-gl-js/v1.3.1/mapbox-gl.js'></script>
<link href='https://api.tiles.mapbox.com/mapbox-gl-js/v1.3.1/mapbox-gl.css' rel='stylesheet' />
<style>
  #map { 
    position: top:0; bottom:0; height: 400px; max-width: 100%; 
  }
  .marker {
    background-image: url('../assets/img/poi.png');
    background-size: cover;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
  }
  .mapboxgl-popup {
    max-width: 200px;
  }

  .mapboxgl-popup-content {
    text-align: center;
    font-family: 'Open Sans', sans-serif;
  }
</style>
  
- [Registration](#registration)
- [Accomodation](#accomodation)
- [Venues](#venues)
- [Travel](#travel)

<h3 id="registation">Registration</h3>  
The registration for ICLI is now OPEN. go to [this link](https://ntnu.eventsair.com/icli2020/registration) to register.
Early bird registration give a reduced price and is open until January 30th. It is possible to register (full price) up until the conference starts.
The conference fee is reduced for participants without an institutional affiliation, to support participation for independent artists and researchers. Bachelor and master students may  use the reduced fee too.


##### Prices
Full conference fee: 330 EUR, with an early bird price of 250 EUR  
The reduced fee for independent artists and students: 170 EUR, with an early bird fee of 130 EUR.

The conference fee includes access to all the events, coffee and lunch for all three days, a copy of the Meta.Morf catalogue, and inclusion of your submission in the proceedings. You also get free entrance to the Meta.Morf exhibition at Gråmølna [https://trondheimkunstmuseum.no/tkm-gramolna](https://trondheimkunstmuseum.no/tkm-gramolna)


<h3 id="accomodation">Accomodation</h3>

Below are some recommended accomodation possibilities.

###### Quality Hotel Augustin

![Quality Hotel Augustin](/assets/img/Quality-Hotel-Augustin.jpg)

**Special prices for ICLI participants**:

- Single room: 1050 NOK
- Double room: 1250 NOK

**The rooms must be booked directly with the hotel** (phone +47 73 54 70 00). The booking must be done **at least 3 weeks before the conference** starts to ensure availability.

Use reference number "4857" when booking to get these ICLI prices.

The booking must be done at least 3 weeks before the conference starts to ensure availability.

###### Comfort Hotel Park

![Comfort Park](/assets/img/Comfort-Hotel-Park.jpg)

**Prices:**

- Single room: 1123 NOK
- Double room: 1340 NOK

**Contact**

- Website: [Comfort Hotel Park](https://www.nordicchoicehotels.no/hotell/norge/trondheim/comfort-hotel-park/)
- Email: [co.park@choice.no](mailto:co.park@choice.no)
- Phone: +47 73833900
- Fax: +47 73833901

###### Other options

- [Nordic Choice Hotels](https://www.nordicchoicehotels.com/hotels/norway/trondheim)
- [Thon Hotels](https://www.thonhotels.com/our-hotels/norway/trondheim/thon-hotel-trondheim/)
- [Scandic Hotels](https://www.scandichotels.com/hotels/norway/trondheim)
- [Radisson Blue Royal Garden](https://www.radissonhotels.com/en-us/hotels/radisson-blu-trondheim-royal-garden)
- [Nidaros Pilegrimsgård](http://pilegrimsgarden.pilegrimsleden.no/)
- [Trondheim Vandrerhjem](http://www.trondheimvandrerhjem.no/en/home.html)


<h3 id="venues">Venues</h3>  



<div id='map'></div>

<script>
  mapboxgl.accessToken = 'pk.eyJ1IjoibGl2ZWludGVyZmFjZXMiLCJhIjoiY2swcDZ5Mno3MGYxdjNnbjZmYmJsdHJkaSJ9.bfcq3YulwNY3JekbxvASOQ';
   
  var map = new mapboxgl.Map({
    container: 'map',
    style: 'mapbox://styles/mapbox/streets-v9',
    center: [10.406494, 63.434764],
    zoom: 12
  });
   
  var geojson = {
    type: 'FeatureCollection',
    features: [{
      type: 'Feature',
      geometry: {
        type: 'Point',
        coordinates: [10.401446, 63.438835]
      },
      properties: {
        title: 'Rockheim',
        description: 'Brattørkaia 14, 7010 Trondheim'
      }
    },
    {
      type: 'Feature',
      geometry: {
        type: 'Point',
        coordinates: [10.411141, 63.434183]
      },
      properties: {
        title: 'Dokkhuset',
        description: 'Dokkparken 4, 7042 Trondheim'
      }
    },
    {
      type: 'Feature',
      geometry: {
        type: 'Point',
        coordinates: [10.395398, 63.426880]
      },
      properties: {
        title: 'Nidarosdomen',
        description: 'Kongsgårdsgata 2, 7013 Trondheim'
      }
    }]
  };
   
  map.on('load', function () {
    geojson.features.forEach(function(marker) {
      // create a HTML element for each feature
      var el = document.createElement('div');
      el.className = 'marker';

      // make a marker for each feature and add to the map
      new mapboxgl.Marker(el)
      .setLngLat(marker.geometry.coordinates)
      // add popups
      .setPopup(new mapboxgl.Popup({ offset: 25, maxWidth: 150, anchor: 'left' })
        .setHTML(
          '<h5>' + marker.properties.title + '</h5>' + 
          '<p>' + marker.properties.description + '</p>' + 
          // use the (...)_thumb.jpg images
          '<img src=\'../assets/img/' + marker.properties.title.toLowerCase() + '_thumb.jpg\'></img>'
        ))
      .addTo(map);
    });
  });
 
</script>
[Rockheim](https://rockheim.no/) is the National Museum of Popular Music that collects, preserve and disseminates
Norwegian popular music from the 1950s until today. Rockheim is located on the Brattørkaia in Trondheim. The keynote and concert Tuesday evening at 19.00 happense here. 

[Dokkhuset](http://dokkhuset.no/) is a concert venue at Nedre Elvehavn in Trondheim. The Dokkhuset scene presents chamber music and jazz, new music, world music and other forms of musical expression. The daytime sessions all three days of the ceonference happens here.

[Nidaros Cathedral](https://www.nidarosdomen.no/en/) is the world’s northernmost medieval cathedral and Norway’s national sanctuary. The reception concert Monday night at 19.00 happens here.

<h3 id="travel">Travel to Trondheim</h3>  

Værnes Airport Trondheim has national and international flight connections.
There are two companies offering direct bus services into Trondheim City, departing every 15min.  

* [Værnes Ekspressen](https://vaernesekspressen.no/)

The train travels along the coast line to Trondheim Sentrum and offers a beautiful landscape, it
runs once every hour. 

You can also travel to Trondheim by train from Oslo. The train from Oslo to to Trondheim also pass Gardermoen airport.
Web site for train timetables and tickets: [vy.no](https://www.vy.no/en)

<h3>Travel within Trondheim</h3>

Info on bus/tram/taxi
[AtB](https://www.atb.no/en/), transport company in Trondheim. Tickets can be purchased with mobile app “Mobillett” or SMS. Single tickets are 38 NOK and lasts 90 minutes. 24-hour tickets are 114 NOK, and 7 day tickets are 266 NOK. 
It is also possible to buy tickets at selected "Narvesen", "7-Eleven" og "Coop" shops. Paying on-board using cash is not possible
Zone A covers the city center entirely.

Taxi phone numbers
Trøndertaxi +47 930 07373 (calling from abroad) or 07373 (calling from Norway)
Norges taxi +47 930 08000 (calling from abroad) or 08000 (calling from Norway)