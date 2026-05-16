<template>
  <section id="menu">
    <header>
      <div id="menu-container">
        <!-- LOGO TP + NOME -->
        <router-link id="logo-block" to="/">
          <img :src="logoImg" alt="Dr. Teresa Polimeno" id="img-logo" />
          <div class="logo-text-wrap">
            <span class="logo-name">Dr. Teresa</span>
            <span class="logo-surname">Polimeno</span>
          </div>
        </router-link>

        <!-- HAMBURGER MOBILE -->
        <div class="col-xs-6" id="mobile-view">
          <div class="hamburger-wrap">
            <button class="hamburger" type="button" @click="openCloseSidebar">
              <span class="hamburger__line"></span>
              <span class="hamburger__line"></span>
              <span class="icon-bar hamburger__line"></span>
            </button>
          </div>
        </div>

        <!-- MENU DESKTOP -->
        <div id="desktop-view">
          <router-link to="/" class="nav-link">HOME</router-link>
          <router-link to="/contacts" id="btn-prenota">PRENOTA UNA VISITA</router-link>
        </div>
      </div>

      <div>
        <div class="row dropdown" :class="{ 'dropdown-after': menuOpen }">
          <p class="navlistitem">
            <router-link to="/">HOME</router-link>
          </p>
          <p class="navlistitem">
            <router-link to="/contacts">Prenota una visita</router-link>
          </p>
        </div>
      </div>
    </header>
  </section>
</template>

<script>
import logoImg from '@/assets/images/logo.svg'

export default {
  name: 'Menu',

  data() {
    return {
      menuOpen: false,
      logoImg
    }
  },

  methods: {
    openCloseSidebar() {
      this.menuOpen = !this.menuOpen
    }
  }
}
</script>

<style scoped lang="scss">
$accent: #a6d1e8;

#desktop-view {
  display: none;
}

#menu {
  position: sticky;
  top: 0;
  z-index: 100;

  header {
    background: #f5f5f5;
    border-bottom: 3px solid $accent;
  }

  #menu-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 20px;
    #logo-block {
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
      color: #2c2c2c;
    }
    #img-logo {
      height: 42px;
      width: auto;
      display: block;
      flex-shrink: 0;
    }
    .logo-text-wrap {
      display: flex;
      flex-direction: column;
      gap: 2px;
      line-height: 1.2;
    }
    .logo-name {
      font-size: 1rem;
      font-weight: 600;
      font-style: italic;
      color: $accent;
      letter-spacing: 0.01em;
    }
    .logo-surname {
      font-size: 1.05rem;
      font-weight: 600;
      font-style: italic;
      color: $accent;
      letter-spacing: 0.02em;
    }
    #logo-block:hover {
      #img-logo {
        opacity: 0.9;
      }
    }
    .hamburger-wrap {
      width: 100px;
      height: 100%;
      display: flex;
      align-items: center;
      float: right;
      justify-content: flex-end;
      .hamburger {
        width: 45px;
        height: 45px;
        background-color: transparent;
        border-radius: 4px;
        border: none;
      }
      .hamburger:focus {
        outline: none;
      }
      .hamburger__line,
      .hamburger__middle {
        display: block;
        height: 5px;
        border-radius: 2px;
        background-color: $accent;
        margin-top: 7px;
        margin-bottom: 7px;
      }
      .hamburger__middle {
        width: 20px;
        margin-left: 10px;
      }
    }
  }

  @media (max-width: 768px) {
    header {
      padding: 4px 0;
    }
    #menu-container {
      min-height: 56px;
      padding: 12px 20px;
    }
    #menu-container .logo-text-wrap {
      display: none;
    }
    #menu-container #img-logo {
      height: 34px;
    }
  }

  .dropdown {
    height: 0px;
    background-color: #fafafa;
    transition: height 0.2s ease;
    display: flex;
    flex-direction: column;
    align-items: stretch;
    justify-content: space-around;
    overflow: hidden;
    position: fixed;
    width: -webkit-fill-available;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    .navlistitem {
      text-transform: uppercase;
      text-align: center;
      margin: 0;
    }
    .navlistitem a {
      color: black;
      text-decoration: none;
      font-size: 1.05rem;
      padding: 16px 24px;
      min-height: 48px;
      box-sizing: border-box;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }

  .dropdown-after {
    height: calc(30vh - 50px);
    transition: height 0.2s ease;
  }
}

@media only screen and (min-width: 769px) {
  #mobile-view {
    display: none;
  }

  header {
    display: flex;
    justify-content: space-between;
    padding: 18px 40px;
    box-shadow: 0 1px 0 rgba(0, 0, 0, 0.06);
    background: #f5f5f5;
    #menu-container {
      width: 100%;
      max-width: none;
      .logo-name {
        font-size: 1.05rem;
      }
      .logo-surname {
        font-size: 1.15rem;
      }
      #desktop-view {
        display: flex;
        align-items: center;
        gap: 4px;
        margin-left: auto;
        .nav-link {
          text-decoration: none;
          text-transform: uppercase;
          color: $accent;
          font-size: 14px;
          font-weight: 600;
          letter-spacing: 0.03em;
          padding: 10px 20px;
          border-radius: 6px;
          transition:
            color 0.2s,
            background 0.2s;
        }
        .nav-link:hover {
          color: darken($accent, 12%);
          background: rgba(188, 141, 183, 0.1);
        }
        #btn-prenota {
          background: $accent;
          color: white !important;
          text-decoration: none;
          text-transform: uppercase;
          font-size: 13px;
          font-weight: 700;
          letter-spacing: 0.04em;
          padding: 14px 28px;
          border-radius: 10px;
          margin-left: 12px;
          transition:
            background 0.2s,
            transform 0.2s;
          box-shadow: 0 2px 8px rgba(188, 141, 183, 0.35);
        }
        #btn-prenota:hover {
          background: darken($accent, 8%);
          transform: translateY(-1px);
          box-shadow: 0 4px 12px rgba(188, 141, 183, 0.4);
        }
      }
    }
  }
}
</style>
