<template>
  <div id="map-wrap">
    <router-link to="/" class="mainMapLink">
      <a>To Top</a>
    </router-link>
    <MglMap
      :accessToken="accessToken"
      :mapStyle="mapStyle"
      :zoom.sync="zoom"
      :center="center"
    >
      <MglNavigationControl />
    </MglMap>
  </div>
</template>

<script lang="js">
import "mapbox-gl/dist/mapbox-gl.css"
import * as vueMapbox from "vue-mapbox"

export default {
  name: "MainMap",
  components: {
    MglMap: vueMapbox.MglMap,
    MglNavigationControl: vueMapbox.MglNavigationControl,
  },
  data() {
    return {
      accessToken: process.env.MAPBOX_API_KEY.
      zoom: 17,
      mapStyle: "mapbox://styles/mapbox/streets-v10",
      center: { lon: 139.7009177, lat: 35.6580971 }
    }
  }
}

</script>
<style>
.mainMapLink {
  position: absolute;
  z-index: 100;
  left: 0;
  padding: 5px;
  margin: 10px;
  background: #42b983;
  border-radius: 10px;
  text-decoration: none;
  color: white;
}
.mapboxgl-canvas {
  outline: transparent;
  left: 0;
}
#map-wrap {
  position: absolute;
  height: 100%;
  top: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
}

#map-wrap .mgl-map-wrapper {
  position: absolute;
  height: 100%;
  top: 0;
  left: 0;
  width: 100%;
}

#map-wrap .mgl-map-wrapper .mapboxgl-map {
  height: 100%;
  left: 0;
  overflow: visible;
  position: absolute;
  top: 0;
  width: 100%;
}

.mapboxgl-ctrl-attrib-inner {
  display: none;
}

.button {
  position: absolute;
  z-index: 100;
  background: rebeccapurple;
}
</style>
