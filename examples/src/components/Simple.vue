<template>
  <div>
    <div id="top_div">
      <h2>Simple</h2>
        Marker is placed at {{ marker.lat }}, {{ marker.lng }}
      </br>
    </div>
    <div id="bottom_div">
      <v-map :zoom="zoom" :center="center">
        <v-tilelayer :url="url" :attribution="attribution"></v-tilelayer>
        <v-marker :lat-lng="marker"></v-marker>
      </v-map>
    </div>
  </div>
</template>

<script>
import Vue2Leaflet from 'vue2-leaflet';

export default {
  name: 'example',
  components: {
    'v-map': Vue2Leaflet.Map,
    'v-tilelayer' :Vue2Leaflet.TileLayer,
    'v-marker': Vue2Leaflet.Marker
  },
  data () {
    return {
      zoom:13,
      center:[47.413220, -1.219482],
      url:'http://{s}.tile.osm.org/{z}/{x}/{y}.png',
      attribution:'&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      marker: L.latLng(47.413220, -1.219482),
    }
  }
}
</script>
