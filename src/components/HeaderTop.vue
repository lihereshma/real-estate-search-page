<template>
  <header class="header-bar">
    <div class="mobile-top-bar">
      <div class="menu-icon"><img src="@/assets/hamburger-icon.png" alt="Menu" loading="lazy" /></div>

      <div class="logo">
        <a href="/" title="Houzeo">
          <img src="@/assets/site-logo.png" alt="Logo" loading="lazy" />
        </a>  
      </div>

      <div class="user-icon">
        <img src="@/assets/user-icon.png" alt="My Account" loading="lazy" />
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
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    background: #fff;
    padding: 0.75rem 2rem;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.07);
    border-bottom: 1px solid #00000033;
    user-select: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
  }

  .mobile-top-bar .menu-icon,
  .mobile-top-bar .user-icon {
    display: none;
  }

  .btns-wrapper {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    gap: 0.75rem;
  }

  .btns-wrapper a {
    text-decoration: none;
    color: #000000;
    font-size: 14px;
    -webkit-transition: all 0.5s ease;
    transition: all 0.5s ease;
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
    -webkit-transition: all 0.5s ease;
    transition: all 0.5s ease;
  }

  .btns-wrapper button:hover {
    background-color: #2876C1;
    color: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  }

  .mobile-top-bar {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    -webkit-box-align: center;
    -ms-flex-align: center;
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
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
    }

    .btns-wrapper {
      display: none;
    }

    .header-bar {
      -ms-flex-wrap: wrap;
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