<template>
  <div class="property-card">
    <!-- Image & Badge -->
    <div class="image-container">
      <img :src="image" alt="Property" class="property-image" />
      <span class="badge">{{ daysOnHouzeo }} days on Houzeo</span>
      <button class="like-button">
        <svg xmlns="http://www.w3.org/2000/svg" class="heart-icon" viewBox="0 0 20 20" fill="currentColor">
          <path d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"/>
        </svg>
      </button>
      <div class="dot-indicators">
        <span v-for="n in 3" :key="n" class="dot"></span>
      </div>
      <img src="@/assets/triangle-mls-logo.png" alt="MLS Logo" class="mls-logo" />
    </div>

    <!-- Content -->
    <div class="content">
      <!-- Top Info -->
      <div class="info-bar">
        <div class="status">
          <span class="status-dot"></span>
          <span>House For Sale</span>
        </div>
        <div class="views">
          <svg xmlns="http://www.w3.org/2000/svg" class="bell-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-5-5.917V4a2 2 0 10-4 0v1.083A6.002 6.002 0 004 11v3.159c0 .538-.214 1.055-.595 1.436L2 17h5m7 0v1a3 3 0 11-6 0v-1m6 0H9"/>
          </svg>
          <span>{{ views }}K</span>
        </div>
      </div>

      <!-- Price -->
      <h3 class="price">{{ price }}</h3>

      <!-- Specs -->
      <div class="specs">
        <span class="bold">{{ beds }}</span> Bds &nbsp;•&nbsp;
        <span class="bold">{{ baths }}</span> Ba &nbsp;•&nbsp;
        <span class="bold">{{ sqft }}</span> sqft &nbsp;•&nbsp;
        <span class="sale-status">Sale Pending</span>
      </div>

      <!-- Address and MLS -->
      <p class="address">{{ address }}</p>
      <p class="mls-details">{{ mlsDetails }}</p>
    </div>
  </div>
</template>

<script setup>
/* eslint-disable no-undef */
defineProps({
  image: String,
  daysOnHouzeo: Number,
  price: String,
  beds: Number,
  baths: Number,
  sqft: Number,
  address: String,
  mlsDetails: String,
  views: Number,
});
</script>

<style scoped>
.property-card {
  width: 100%;
  max-width: 360px;
  border: 1px solid #ddd;
  border-radius: 10px;
  overflow: hidden;
  font-family: 'Poppins', sans-serif;
  background-color: #fff;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.image-container {
  position: relative;
}

.property-image {
  width: 100%;
  height: 210px;
  object-fit: cover;
  display: block;
}

.badge {
  position: absolute;
  top: 8px;
  left: 8px;
  background-color: #ffffff;
  color: #333;
  font-size: 12px;
  padding: 4px 8px;
  border-radius: 9999px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.2);
}

.like-button {
  position: absolute;
  top: 8px;
  right: 8px;
  background-color: white;
  border: none;
  padding: 6px;
  border-radius: 9999px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.2);
  cursor: pointer;
}

.heart-icon {
  width: 20px;
  height: 20px;
  color: #e53e3e;
}

.dot-indicators {
  position: absolute;
  bottom: 8px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 4px;
}

.dot {
  width: 6px;
  height: 6px;
  background-color: rgba(255, 255, 255, 0.7);
  border-radius: 50%;
}

.mls-logo {
  position: absolute;
  bottom: 8px;
  right: 8px;
  width: 80px;
  object-fit: contain;
}

.content {
  padding: 16px;
}

.info-bar {
  display: flex;
  justify-content: space-between;
  font-size: 13px;
  color: #666;
  margin-bottom: 8px;
}

.status {
  display: flex;
  align-items: center;
  gap: 6px;
}

.status-dot {
  width: 8px;
  height: 8px;
  background-color: #22c55e;
  border-radius: 50%;
}

.views {
  display: flex;
  align-items: center;
  gap: 4px;
}

.bell-icon {
  width: 16px;
  height: 16px;
  stroke: #555;
}

.price {
  font-size: 20px;
  font-weight: bold;
  color: #1d4ed8;
  margin-bottom: 8px;
}

.specs {
  font-size: 13px;
  color: #444;
  margin-bottom: 8px;
}

.bold {
  font-weight: 600;
}

.sale-status {
  color: #d97706;
  font-weight: 600;
}

.address {
  font-size: 13px;
  color: #333;
  margin-bottom: 4px;
}

.mls-details {
  font-size: 11px;
  color: #999;
}
</style>
