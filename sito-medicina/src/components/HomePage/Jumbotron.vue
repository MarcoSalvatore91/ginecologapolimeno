<template>
  <section id="jumbotron">
    <div id="container-image">
      <h2 class="content-container-image">Dr. Teresa Polimeno</h2>
      <h3 class="content-container-image">Ginecologa</h3>
      <p class="content-container-image">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus tempora fugit voluptas
        esse neque eum aliquid quia explicabo sint iusto eligendi odio numquam quisquam similique
        eos, quo voluptates quas ex.
      </p>
      <div class="content-container-image">
        <button class="router-btn">Scopri di più</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Jumbotron',

  data() {
    return {}
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#jumbotron {
  #container-image {
    background-color: lightgrey;
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
</style>
