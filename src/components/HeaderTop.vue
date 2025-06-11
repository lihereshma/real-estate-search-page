<template>
  <header class="header-bar">
    <div class="mobile-top-bar">
      <div class="menu-icon"><img src="../assets/hamburger-icon.png" alt="Menu" /></div>

      <div class="logo">
        <img src="../assets/site-logo.png" alt="Logo" />
      </div>

      <div class="user-icon">
        <img src="../assets/user-icon.png" alt="My Account" />
      </div>
    </div>

    <div class="search-wrapper">
      <div class="search-box">
        <input
          v-model="searchLocation"
          type="text"
          placeholder="Austin, TX"
          class="search-input"
        />
        <span class="clear-icon"><img src="../assets/close-icon.png" alt="Close" /></span>
        <span class="search-icon"><img src="../assets/search-icon.png" alt="Search" /></span>
      </div>
    </div>

    <div class="filter-icon">
      <img src="../assets/filter-icon.png" alt="Filter" />
      <!-- <span class="badge">2</span> -->
    </div>

    <div class="btns-wrapper">
      <button class="sign-in-btn">Sign In</button>
      <button class="free-listing-btn">Start Free Listing</button>
    </div>
  </header>
</template>


<script>
export default {
  name: 'HeaderTop'
}
</script>

<style scoped>
.header-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: white;
  padding: 0.75rem 2rem;
  box-shadow: 0 2px 5px rgb(0 0 0 / 0.1);
  user-select: none;
}

.mobile-top-bar .menu-icon,
.mobile-top-bar .user-icon,
.filter-icon {
  display: none;
}

.search-wrapper {
  max-width: 500px;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 10px 16px;
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
  font-size: 14px;
  font-weight: 500;
  transition: border-color 0.3s ease;
  flex: 1;
  font-family: 'Poppins', sans-serif;
}

.search-input:focus {
  border-color: #0E5293;
  outline: 0;
}

.btns-wrapper {
  display: flex;
  gap: 0.75rem;
}

.btns-wrapper button {
  border: none;
  background: linear-gradient(to left, #0E5293, #2876C1);
  color: #fff;
  font-family: 'Poppins', sans-serif;
  font-weight: 500;
  font-size: 14px;
  padding: 8px 16px;
  border-radius: 12px;
  cursor: pointer;
  transition: all 0.5s ease;
}

.btns-wrapper button:hover {
  background: linear-gradient(to right, #0E5293 20%, #2876C1 80%);
  color: #fff;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.mobile-top-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.menu-icon,
.user-icon img {
  width: 24px;
  height: 24px;
  cursor: pointer;
}

.search-box {
  flex: 1;
  display: flex;
  align-items: center;
  border: 2px solid #00000033;
  border-radius: 20px;
  background-color: #F3F7FA;
  padding: 6px 12px;
  position: relative;
}

.search-box input {

}

.search-icon,
.clear-icon {
  font-size: 16px;
  margin-left: 8px;
  color: #0e5293;
  cursor: pointer;
}

.filter-icon {
  position: relative;
  width: 36px;
  height: 36px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.filter-icon img {
  width: 20px;
  height: 20px;
}


/* Responsive */
@media (max-width: 768px) {
  .mobile-top-bar .menu-icon,
  .mobile-top-bar .user-icon,
  .filter-icon {
    display: block;
  }

  .header-bar {
    flex-wrap: wrap;
    padding: 0.5rem 1rem;
  }
  .search-filters-center {
    order: 3;
    width: 100%;
    margin: 0.5rem 0;
  }
  .btns-wrapper {
    order: 2;
  }
  .logo {
    order: 1;
  }
}
</style>