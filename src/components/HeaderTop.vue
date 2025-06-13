<template>
  <header class="header-bar">
    <div class="mobile-top-bar">
      <div class="menu-icon"><img src="@/assets/hamburger-icon.png" alt="Menu" /></div>

      <div class="logo">
        <a href="/" title="Houzeo">
          <img src="@/assets/site-logo.png" alt="Logo" />
        </a>  
      </div>

      <div class="user-icon">
        <img src="@/assets/user-icon.png" alt="My Account" />
      </div>
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

<style>
  .header-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: white;
    padding: 0.75rem 2rem;
    box-shadow: 0 2px 5px rgb(0 0 0 / 0.07);
    border-bottom: 1px solid #00000033;
    user-select: none;
  }

  .mobile-top-bar .menu-icon,
  .mobile-top-bar .user-icon {
    display: none;
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

  @media (max-width: 768px) {
    .mobile-top-bar .menu-icon,
    .mobile-top-bar .user-icon {
      display: flex;
      align-items: center;
    }

    .btns-wrapper {
      display: none;
    }

    .header-bar {
      flex-wrap: wrap;
      padding: 0;
    }

    .mobile-top-bar {
      width: 100%;
      padding: 0.5rem 1rem;
    }

    .logo {
      order: 1;
    }

    .user-icon {
      order: 2;
    }
  }
</style>