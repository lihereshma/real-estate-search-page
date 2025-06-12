<template> 
  <HeaderTop />
  <FilterBar />
  <div class="property-container">
    <LocationMap />
    <PropertyList />
  </div>
  
  
</template>

<script>
import HeaderTop from './components/HeaderTop.vue'
import FilterBar from './components/FilterBar.vue'
import LocationMap from './components/LocationMap.vue'
import PropertyList from './components/PropertyList.vue'


export default {
  name: 'App',
  components: {
    HeaderTop,
    FilterBar,
    LocationMap,
    PropertyList
  }
}
</script>

<style>
#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}

body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
}

.property-container {
  display: flex;
  height: 80vh; /* Full screen height */
}

</style>
