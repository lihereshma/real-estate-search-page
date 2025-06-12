<template>
  <header class="header-bar">
    <div class="mobile-top-bar">
      <div class="menu-icon"><img src="../assets/hamburger-icon.png" alt="Menu" /></div>

      <div class="logo">
        <a href="/" title="Houzeo">
          <img src="../assets/site-logo.png" alt="Logo" />
        </a>  
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
          placeholder="Search by city, state or zip"
          class="search-input"
        />
        <!-- <span class="clear-icon"><img src="../assets/close-icon.png" alt="Close" /></span> -->
        <span class="search-icon"><img src="../assets/search-icon.png" alt="Search" /></span>
      </div>
    </div>

    <div class="filter-icon">
      <img src="../assets/filter-icon.png" alt="Filter" />
      <!-- <span class="badge">2</span> -->
    </div>

    <div class="btns-wrapper">
      <a href="#" class="sign-in-btn">Sign In</a>
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
  /* box-shadow: 0 2px 5px rgb(0 0 0 / 0.1); */
  border-bottom: 1px solid #00000033;
  user-select: none;
}

.mobile-top-bar .menu-icon,
.mobile-top-bar .user-icon,
.filter-icon {
  display: none;
}

.search-wrapper {
  flex: 0 0 30%;
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

.btns-wrapper {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.btns-wrapper a {
  text-decoration: none;
  color: #000000;
  font-size: 14px;
  transition: all .5s ease;
}

.btns-wrapper a:hover {
  color: #0E5293;
}

.btns-wrapper button {
  border: none;
  background-color: #0E5293;
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
  background-color: #2876C1;
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

/* 
.filter-icon img {
  width: 20px;
  height: 20px;
} */


/* Responsive */
@media (max-width: 768px) {
  .mobile-top-bar .menu-icon,
  .mobile-top-bar .user-icon {
    display: flex;
    align-items: center;
  }

  .filter-icon {
    width: 10%;
    margin-right: 1rem;
    display: flex;
    justify-content: flex-end;
    align-items: center;
  }

  .btns-wrapper {
    display: none;
  }

  .header-bar {
    flex-wrap: wrap;
    padding: 0;
  }

  .search-wrapper {
    flex: 0 78%;
    margin: 1rem 0 1rem 1rem;
  }
  .search-filters-center {
    order: 3;
    width: 100%;
    margin: 0.5rem 0;
  }

  .mobile-top-bar {
    width: 100%;
    padding: 0.5rem 1rem;
    border-bottom: 1px solid #00000033;
  }

  .logo {
    order: 1;
  }

  .user-icon {
    order: 2;
  }
}
</style>