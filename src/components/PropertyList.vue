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
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
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
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
    daysOnHouzeo: 12,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
  {
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
    // daysOnHouzeo: 6,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
  {
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
    daysOnHouzeo: 10,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
  {
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
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
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
    // daysOnHouzeo: 10,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
  {
    images: [
      require('@/assets/1.png'),
      require('@/assets/2.png'),
      require('@/assets/3.png'),
    ],
    daysOnHouzeo: 12,
    price: "$3,349,000",
    beds: 4,
    baths: 3,
    sqft: 998,
    address: "2856 Meadow Park Ave, Henderson, NV 89052",
    mlsDetails: "Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID",
    views: 2.3,
  },
];
</script>


<style scoped>
.property-list {
  width: 60%;
  height: 80vh;
  overflow-y: auto;
  padding: 1rem;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: space-between;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

@media (max-width: 768px) {
  .property-list {
    width: 100%;
    max-height: none;
    overflow: visible;
  }
}
</style>