<template>
  <div class="filter-bar">
    <div class="filter-item">
      <label for="status">Status</label>
      <select id="status" class="filter-select">
        <option value="">All</option>
        <option value="For Sale">For Sale</option>
        <option value="Sold">Sold</option>
      </select>
    </div>

    <div class="filter-item">
      <label for="price">Price</label>
      <select id="price" class="filter-select">
        <option value="">Any</option>
        <option value="0-250000">Under $250,000</option>
        <option value="250000-500000">$250,000 - $500,000</option>
        <option value="500000-1000000">$500,000 - $1,000,000</option>
        <option value="1000000+">$1,000,000+</option>
      </select>
    </div>

    <div class="filter-item">
      <label for="bedsBaths">Beds & Baths</label>
      <select id="bedsBaths" class="filter-select">
        <option value="">Any</option>
        <option value="1+">1+</option>
        <option value="2+">2+</option>
        <option value="3+">3+</option>
        <option value="4+">4+</option>
      </select>
    </div>

    <div class="filter-item">
      <label for="propertyType">Property Type</label>
      <select id="propertyType" class="filter-select">
        <option value="">All</option>
        <option value="House">House</option>
        <option value="Condo">Condo</option>
        <option value="Townhouse">Townhouse</option>
      </select>
    </div>

    <button class="additional-filters-btn">Additional Filters</button>
    <button class="save-btn">Save Search</button>

    <!-- Static Modal (optional display) -->
    <!-- <div class="modal-overlay">
      <div class="modal-content">
        <h3>Additional Filters</h3>
        <p>This is a placeholder for advanced filters.</p>
        <button class="modal-close-btn">Close</button>
      </div>
    </div> -->
  </div>
</template>

<style scoped>
.filter-bar {
  display: flex;
  align-items: center;
  gap: 1rem;
  background: white;
  padding: 0.75rem 2rem;
  box-shadow: 0 2px 5px rgb(0 0 0 / 0.07);
  user-select: none;
  flex-wrap: wrap;
  justify-content: center;
}

.filter-item {
  display: flex;
  flex-direction: column;
}

.filter-item label {
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 0.25rem;
  color: #555;
}

.filter-select {
  padding: 0.4rem 0.75rem;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-size: 0.9rem;
  transition: border-color 0.3s ease;
  outline-offset: 2px;
  min-width: 120px;
  cursor: pointer;
}

.filter-select:focus {
  border-color: #3b82f6;
}

.additional-filters-btn,
.save-btn {
  padding: 0.5rem 1rem;
  border: 2px solid #3b82f6;
  border-radius: 8px;
  background-color: transparent;
  color: #3b82f6;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.3s ease;
  white-space: nowrap;
}

.additional-filters-btn:hover,
.save-btn:hover {
  background-color: #3b82f6;
  color: white;
}

/* Modal style */
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
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  border: none;
  background: #3b82f6;
  color: white;
  font-weight: 600;
  cursor: pointer;
}

/* Responsive */
@media (max-width: 768px) {
  .filter-bar {
    padding: 0.5rem 1rem;
  }

  .filter-item {
    min-width: 120px;
    flex: 1 1 40%;
  }

  .additional-filters-btn,
  .save-btn {
    flex: 1 1 100%;
  }
}
</style>
