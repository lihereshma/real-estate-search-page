<template>
  <div class="property-card">
    <div class="image-container" @mouseenter="showNav = true" @mouseleave="showNav = false">
      <img v-if="images && images.length" :src="images[currentImage]" alt="Property" class="property-image" />

      <span v-if="daysOnHouzeo" class="badge">
        {{ daysOnHouzeo }} days on Houzeo
      </span>

      <button class="like-button">
        <img src="@/assets/heart.svg" alt="Like" class="heart-icon" />
      </button>

      <div class="dot-indicators" v-if="showNav">
        <span v-for="n in 3" :key="n" class="dot"></span>
      </div>

      <button
        v-if="showNav"
        class="nav-arrow left"
        @click="prevImage">&#10094;</button>

      <button
        v-if="showNav"
        class="nav-arrow right"
        @click="nextImage">&#10095;</button>

      <img src="@/assets/triangle-mls-logo.png" alt="MLS Logo" class="mls-logo" />
    </div>

    <div class="content">
      <div class="info-bar">
        <div class="status">
          <span class="status-dot"></span>
          <span>House For Sale</span>
        </div>

        <div class="views">
          <img src="../assets/views-icon.png" alt="Views" class="views-icon" />
          <span>{{ views }}K</span>
        </div>
      </div>

      <div class="info-bar">
        <h3 class="price">{{ price }}</h3>

        <div class="specs">
          <span class="bold">{{ beds }}</span> Beds &nbsp;•&nbsp;
          <span class="bold">{{ baths }}</span> Baths &nbsp;•&nbsp;
          <span class="bold">{{ sqft }}</span> sqft
        </div>
      </div>

      <p class="address">{{ address }}</p>
      <p class="mls-details">{{ mlsDetails }}</p>
    </div>
  </div>
</template>

<script setup>
  /* eslint-disable no-undef */
  import { ref } from 'vue';

  const props = defineProps({
    images: {
      type: Array,
      required: true,
    },
    daysOnHouzeo: Number,
    price: String,
    beds: Number,
    baths: Number,
    sqft: Number,
    address: String,
    mlsDetails: String,
    views: Number,
  });

  const currentImage = ref(0);
  const showNav = ref(false);

  const nextImage = () => {
    currentImage.value = (currentImage.value + 1) % props.images.length;
  };

  const prevImage = () => {
    currentImage.value = (currentImage.value - 1 + props.images.length) % props.images.length;
  };
</script>

<style scoped>
.property-card {
  flex: 0 0 calc(50% - 12px);
  border: 1px solid #ddd;
  border-radius: 16px;
  overflow: hidden;
  font-family: 'Poppins', sans-serif;
  background-color: #fff;
  cursor: pointer;
  transition: all .5s ease;
}

.property-card:hover {
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.image-container {
  position: relative;
}

.property-image {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
}

.badge {
  position: absolute;
  top: 16px;
  left: 16px;
  background-color: #ffffff;
  color: #000;
  font-size: 14px;
  font-weight: 500;
  padding: 4px 8px;
  border-radius: 9999px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.2);
}

.like-button {
  position: absolute;
  top: 16px;
  right: 16px;
  background-color: transparent;
  border: none;
  border-radius: 9999px;
  padding: 0;
  cursor: pointer;
}

.heart-icon {
  width: 24px;
  height: 24px;
}

.like-button:hover .heart-icon {
  animation: pulse 0.6s ease-in-out;
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}

.nav-arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255, 253, 253, 0.5);
  color: #000;
  border: none;
  font-size: 16px;
  padding: 2px 8px;
  cursor: pointer;
  border-radius: 50%;
  z-index: 2;
  transition: all 0.5s ease;
}

.nav-arrow:hover {
  background: #fff;
}

.nav-arrow.left {
  left: 10px;
}

.nav-arrow.right {
  right: 10px;
}

.dot-indicators {
  position: absolute;
  bottom: 12px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 6px;
  transition: all .5s ease;
}

.dot {
  width: 8px;
  height: 8px;
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  transition: background-color 0.3s ease;
}

.dot.active {
  background-color: #fff;
}

.mls-logo {
  position: absolute;
  bottom: 8px;
  right: 8px;
}

.content {
  padding: 16px;
}

.info-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 13px;
  color: #666;
  margin-bottom: 8px;
}

.status {
  display: flex;
  align-items: center;
  gap: 6px;
  border: 1px solid #0000001A;
  border-radius: 50px;
  padding: 2px 8px;
}

.status-dot {
  width: 10px;
  height: 10px;
  background-color: #22c55e;
  border-radius: 50%;
}

.views {
  display: flex;
  align-items: center;
  gap: 4px;
  cursor: pointer;
  color: #000000;
  opacity: .7;
  transition: all .5s ease;
}

.views:hover {
  opacity: 1;
}

.price {
  font-size: 16px;
  font-weight: 600;
  color: #0B5AA5;
  margin: 0;
}

.specs {
  font-size: 12px;
  color: #00000080;
}

.bold {
  font-size: 14px;
  font-weight: 600;
  color: #0B5AA5;
}

.address {
  font-size: 12px;
  color: #000000B2;
  margin-bottom: 4px;
  text-align: left;
}

.mls-details {
  margin-bottom: 0;
  font-size: 12px;
  color: #00000080;
  text-align: left;
}

@media (max-width: 640px) {
  .property-card {
    flex: 0 0 100%;
  }
}

@media (min-width: 1920px) {
  .property-card {
    flex: 0 0 calc(33% - 12px);
  }
}
</style>
