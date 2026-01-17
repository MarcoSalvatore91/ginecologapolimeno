<template>
  <section id="jumbotron" :style="{ backgroundImage: `url(${tracyImage})` }">
    <div id="container-image">
      <h2 class="content-container-image">Dr. Teresa Polimeno</h2>
      <h3 class="content-container-image">Specialista in Ginecologia  e Ostetricia</h3>
      <!-- <p class="content-container-image">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus tempora fugit voluptas
        esse neque eum aliquid quia explicabo sint iusto eligendi odio numquam quisquam similique
        eos, quo voluptates quas ex.
      </p> -->
      <!-- <div class="content-container-image">
        <button class="router-btn">Scopri di più</button>
      </div> -->
    </div>
  </section>
</template>

<script>
import tracyImage from '@/assets/images/tracy.jpg'

export default {
  name: 'Jumbotron',

  data() {
    return {
      tracyImage
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#jumbotron {
  background-color: lightgrey;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: white;
  #container-image {
    align-content: center;
    align-items: center;
    padding: 15px 20px 15px 20px;
    text-align: center;
    .content-container-image {
      padding: 10px 0;
    }
    .content-container-image:first-child {
      padding-top: 0;
      padding-bottom: 0;
    }
  }
}

/* Responsive Desktop */

@media only screen and (min-width: 769px) {
  #jumbotron {
    #container-image {
      width: 80%;
      padding: 50px 200px;
      text-align: left;
      .content-container-image .router-btn {
        transition:
          background-color 0.3s ease,
          color 0.3s ease;
      }
      .content-container-image .router-btn:hover {
        color: white;
        background-color: #d97cb1;
      }
      .content-container-image:first-child {
      }
    }
  }
}
</style>
