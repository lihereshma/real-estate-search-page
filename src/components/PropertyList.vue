<template>
  <div class="property-list">
    <PropertyCard
      v-for="property in properties"
      :key="property.id"
      :property="property"
      @toggleFavorite="toggleFavorite"
    />
  </div>
</template>

<script>
export default {
  name: 'PropertyList'
}
</script>

<style scoped>
.property-list {
  width: 60%;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  overflow-y: auto;
  max-height: 100%;
  padding-right: 1rem;
}

/* Mobile stack - full width property card */
@media (max-width: 768px) {
  .property-list {
    padding-right: 0;
    max-height: none;
  }
}
</style>