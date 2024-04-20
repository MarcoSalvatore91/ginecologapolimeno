<template>
  <section id="menu">
    <header>
      <div id="menu-container">
        <!-- LOGO -->
        <img id="img-logo" src="@/assets/logo.svg" alt="logo" />

        <!-- HOME -->
        <div class="col-xs-6">
          <div class="hamburger-wrap">
            <button class="hamburger" type="button" @click="openCloseSidebar">
              <span class="hamburger__line"></span>
              <span class="hamburger__line"></span>
              <span class="icon-bar hamburger__line"></span>
            </button>
          </div>
        </div>
      </div>

      <!-- MENU -->
      <div class="row dropdown" :class="{ 'dropdown-after': menuOpen }">
        <p class="navlistitem">
          <a href="#">home</a>
        </p>
        <p class="navlistitem">
          <a href="#">about</a>
        </p>
        <p class="navlistitem">
          <a href="#">contact</a>
        </p>
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
#menu {
  #menu-container {
    display: flex;
    justify-content: space-between;
    margin: 30px 20px;
    #img-logo {
      height: 45px;
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
        background-color: lightblue;
        border-radius: 4px;
        border: none;
      }
      .hamburger:focus {
        outline: none;
      }
      .hamburger__line,
      .hamburger__middle {
        display: block;
        height: 2px;
        border-radius: 2px;
        background-color: #ffffff;
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
    background-color: red;
    transition: height 0.2s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    overflow: hidden;
    position: fixed;
    width: 100%;
    .navlist {
      list-style: none;
      .navlistitem {
        text-transform: uppercase;
        text-align: center;
        padding: 20px;
      }
      .navlistitem a {
        color: #ffffff;
      }
    }
  }

  .dropdown-after {
    height: calc(30vh - 50px);
    transition: height 0.2s ease;
  }
}
</style>
