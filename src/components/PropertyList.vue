<template>
  <div class="property-list">
    <PropertyCard 
      v-for="(property, index) in properties" 
      :key="index" 
      v-bind="property" 
    />

  </div>
</template>

<script setup>
import PropertyCard from './PropertyCard.vue';

const properties = [
  {
    image: require('@/assets/1.png'),
    daysOnHouzeo: 6,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
  {
    image: require('@/assets/2.png'),
    daysOnHouzeo: 10,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
  // You can add more properties here
];
</script>


<style scoped>
.property-list {
  width: 60%;
  padding: 1rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  max-height: 100%;
}

/* Mobile stack - full width property card */
@media (max-width: 768px) {
  .property-list {
    padding-right: 0;
    max-height: none;
  }
}
</style>