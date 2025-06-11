<template>
  <section class="map-container" ref="mapContainer"></section>
</template>

<script>
export default {
  name: 'LocationMap'
}
</script>

<style>
.map-container {
  width: 40%;
  height: 100%;
  overflow: hidden;
  box-shadow: 0 4px 15px rgb(0 0 0 / 0.15);
  background-color: red;
}

/* Mobile style - map collapsed behind or smaller */
@media (max-width: 768px) {
  .map-container {
    width: 100%;
    height: 180px;
    margin-bottom: 1rem;
  }
}
</style>