<template>
  <div class="cards-container">
    <div class="sort-bar">
      <label for="sort">Sort By:</label>
      <select id="sort" class="sort-dropdown">
        <option value="new">New Listing</option>
        <option value="price-low-high">Price: Low to High</option>
        <option value="price-high-low">Price: High to Low</option>
        <option value="most-viewed">Most Viewed</option>
      </select>
    </div>

    <div class="property-list">
      <PropertyCard 
        v-for="(property, index) in properties" 
        :key="index" 
        v-bind="property" 
      />
    </div>
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


<style>
  .cards-container {
    width: 60%;
    padding-top: 1rem;
    display: flex;
    flex-direction: column;
  }

  .property-list {
    padding-top: 0;
    height: 80vh;
    overflow-y: auto;
    padding: 1rem;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    gap: 20px;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    box-sizing: border-box;
    -webkit-overflow-scrolling: touch;
    scroll-behavior: smooth;
  }

  .sort-bar {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    justify-content: flex-end;
    margin-bottom: 1rem;
    padding: 0 1rem;
    font-family: 'Poppins', sans-serif;
  }

  .sort-bar label {
    margin-right: 0.5rem;
    font-weight: 500;
    font-size: 14px;
    color: #000;
  }

  .sort-dropdown {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    padding: 6px 12px;
    font-size: 14px;
    color: #000;
    border: 1px solid #ccc;
    border-radius: 8px;
    background-color: #fff;
    cursor: pointer;
    padding-right: 30px;
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg fill='black' height='16' viewBox='0 0 24 24' width='16' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M7 10l5 5 5-5z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    background-size: 16px;
    transition: all .5s ease;
  }

  .sort-dropdown::-ms-expand {
    display: none;
  }

  .sort-dropdown:focus {
    border-color: #0B5AA5;
    outline: none;
    background-color: #F3F7FA;
  }

  @media (max-width: 768px) {
    .cards-container {
      width: 100%;
    }

    .property-list {
      max-height: none;
      overflow: visible;
    }
  }
</style>