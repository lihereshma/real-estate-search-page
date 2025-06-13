<template>    
  <div class="filter-bar">
    <div class="search-wrapper">
      <div class="search-box">
        <input       
          type="text"
          placeholder="Search by city, state or zip"
          class="search-input"
        />
        <!-- <span class="clear-icon"><img src="@/assets/close-icon.png" alt="Close" /></span> -->
        <span class="search-icon"><img src="@/assets/search-icon.png" alt="Search" /></span>
      </div>
    </div>

    <div class="filter-icon" @click="toggleFilters">
      <img src="@/assets/filter-icon.png" alt="Filter" />
    </div>

    <div class="filters" :class="{ show: showFilters }">
      <select id="status" class="filter-select active">
        <option value="For Sale" selected>For Sale</option>
        <option value="Sold">Sold</option>
      </select>

      <select id="price" class="filter-select">
        <option value="">Price</option>
        <option value="0-250000">Under $250K</option>
        <option value="250000-500000">$250K - $500K</option>
        <option value="500000-1000000">$500K - $1M</option>
        <option value="1000000+">$1M+</option>
      </select>

      <select id="bedsBaths" class="filter-select">
        <option value="">Beds & Baths</option>
        <option value="1+">1+</option>
        <option value="2+">2+</option>
        <option value="3+">3+</option>
        <option value="4+">4+</option>
      </select>

      <select id="propertyType" class="filter-select">
        <option value="">Property Type</option>
        <option value="House">House</option>
        <option value="Condo">Condo</option>
        <option value="Townhouse">Townhouse</option>
      </select>

      <button class="additional-filters-btn" @click="showModal = true">
        <img src="@/assets/filters-icon.png" alt="Filters" />Filters
      </button>

      <button class="save-btn">
        <img src="@/assets/edit-icon.png" alt="SAve Search" />Save Search
      </button>
    </div>

    <div class="modal-overlay" v-if="showModal">
      <div class="modal-content">
        <h3>Additional Filters</h3>
        <p>This is a modal for Additional Filters</p>
        <button class="modal-close-btn" @click="showModal = false">Close</button>
      </div>
    </div>
  </div>
</template>

<script setup>
  import { ref } from 'vue';

  const showModal = ref(false);

  const showFilters = ref(false);

  function toggleFilters() {
    showFilters.value = !showFilters.value;
  }
</script>


<style>
  .filter-icon {
    display: none;
  }

  .search-wrapper {
    flex: 0 0 25%;
  }

  .search-filters-center {
    flex: 1;
    max-width: 600px;
    margin: 0 1rem;
    display: flex;
    justify-content: center;
  }

  .search-input {
    width: 100%;
    padding: 10px 16px;
    border: 2px solid #00000033;
    border-radius: 50px;
    background-color: #F3F7FA;
    font-size: 14px;
    font-weight: 500;
    transition: border-color 0.3s ease;
    flex: 1;
    font-family: 'Poppins', sans-serif;
    box-sizing: border-box;
  }

  .search-input:focus {
    border-color: #0E5293;
    outline: 0;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  }

  .search-box {
    flex: 1;
    position: relative;
  }

  .search-icon {
    position: absolute;
    right: 7px;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    align-items: center;
    cursor: pointer;
  }

  .search-icon img {
    transition: all .5s ease;
  }

  .search-icon:hover img {
    transform: scale(1.05);
  }

  .filter-bar {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 1rem;
    background: #fff;
    padding: 0.75rem 2rem;
    box-shadow: 0 2px 5px rgb(0 0 0 / 0.07);
    user-select: none;
    flex-wrap: wrap;
  }

  .filters {
    flex: 0 0 70%;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    gap: 1rem;
  }

  .filter-select {
    padding: 10px 16px;
    border: 1px solid #00000033;
    border-radius: 8px;
    font-size: 14px;
    transition: all 0.3s ease;
    min-width: 150px;
    cursor: pointer;
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none;  
    background-image: url("data:image/svg+xml,%3Csvg fill='black' height='16' viewBox='0 0 24 24' width='16' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M7 10l5 5 5-5z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    background-size: 16px;
  }

  .filter-select:focus {
    border-color: #0B5AA5;
    outline: none;
    background-color: #F3F7FA;
  }

  .save-btn {
    display: flex;
    align-items: center;
    gap: 1em;
    padding: 10px 16px;
    border: 1px solid #00000033;
    border-radius: 50px;
    background-color: transparent;
    color: #000;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.5s ease;
    white-space: nowrap;
  }

  .save-btn:hover {
    border-color: #000;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  }

  .additional-filters-btn {
    padding: 10px 16px;
    border: 1px solid #00000033;
    border-radius: 8px;
    font-size: 14px;
    transition: all 0.3s ease;
    background-color: transparent;
    color: #000;
    cursor: pointer;
    transition: all 0.3s ease;
    white-space: nowrap;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 15px;
  }

  .additional-filters-btn:hover {
    border-color: #0B5AA5;
    outline: none;
    background-color: #F3F7FA;
  }

  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgb(0 0 0 / 0.3);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 999;
  }

  .modal-content {
    background: white;
    padding: 2rem;
    border-radius: 12px;
    max-width: 400px;
    width: 100%;
    box-shadow: 0 8px 20px rgb(0 0 0 / 0.25);
    text-align: center;
  }

  .modal-close-btn {
    border: none;
    background-color: #0E5293;
    color: #fff;
    font-family: 'Poppins', sans-serif;
    font-weight: 500;
    font-size: 14px;
    padding: 8px 30px;
    border-radius: 12px;
    cursor: pointer;
    transition: all 0.5s ease;
  }

  .modal-close-btn:hover {
    background-color: #2876C1;
    color: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  }

  @media (max-width: 768px) {
    .filters {
      flex-wrap: wrap;
      flex: 0 0 100%;
      gap: 10px;
      max-height: 0;
      overflow: hidden;
      opacity: 0;
      transform: translateY(-10px);
      transition: all 0.3s ease-in-out;
    }

    .filters.show {
      max-height: 500px;
      padding-bottom: 1rem;
      opacity: 1;
      transform: translateY(0);
    }

    .filter-bar {
      padding: 1rem;
      border-radius: 0 0 20px 20px;
      padding-bottom: 0;
      justify-content: space-between;
    }

    .filter-icon {
      width: 10%;
      display: flex;
      justify-content: flex-end;
      align-items: center;
    }

    .filter-select {
      font-size: 12px;
      min-width: 126px;
    }

    .search-wrapper {
      flex: 0 85%;
    }
    
    .search-filters-center {
      order: 3;
      width: 100%;
      margin: 0.5rem 0;
    }
    
    .additional-filters-btn,
    .save-btn {
      flex: none;
      font-size: 12px;
    }

    #propertyType {
      min-width: 144px;
    }
  }
</style>
