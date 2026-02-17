<template>
  <section id="menu">
    <header>
      <div id="menu-container">
        <!-- LOGO TP + NOME -->
        <router-link id="logo-block" to="/">
          <div id="img-logo-circle">TP</div>
          <span id="logo-text">Dr. Teresa Polimeno</span>
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
export default {
  name: 'Menu',

  data() {
    return {
      menuOpen: false
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
$accent: #d97cb1;

#desktop-view {
  display: none;
}

#menu {
  position: sticky;
  top: 0;
  z-index: 100;

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
    #img-logo-circle {
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: $accent;
      color: white;
      font-weight: bold;
      font-size: 17px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    #logo-text {
      font-weight: 600;
      font-size: 1.1rem;
    }
    #logo-block:hover {
      #img-logo-circle {
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

  .dropdown {
    height: 0px;
    background-color: #fafafa;
    transition: height 0.2s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
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
      font-size: 18px;
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
      #logo-text {
        font-size: 1.05rem;
        font-weight: 600;
        color: #2c2c2c;
      }
      #desktop-view {
        display: flex;
        align-items: center;
        gap: 4px;
        margin-left: auto;
        .nav-link {
          text-decoration: none;
          text-transform: uppercase;
          color: #2c2c2c;
          font-size: 14px;
          font-weight: 600;
          letter-spacing: 0.03em;
          padding: 10px 20px;
          border-radius: 6px;
          transition: color 0.2s, background 0.2s;
        }
        .nav-link:hover {
          color: $accent;
          background: rgba(217, 124, 177, 0.06);
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
          transition: background 0.2s, transform 0.2s;
          box-shadow: 0 2px 8px rgba(217, 124, 177, 0.35);
        }
        #btn-prenota:hover {
          background: #c46a9d;
          transform: translateY(-1px);
          box-shadow: 0 4px 12px rgba(217, 124, 177, 0.4);
        }
      }
    }
  }
}
</style>
