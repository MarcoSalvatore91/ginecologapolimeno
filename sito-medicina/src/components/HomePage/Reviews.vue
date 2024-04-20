<template>
  <section id="reviews">
    <div id="reviews-container"></div>
    <h2 id="title-reviews">Recensioni Dei Nostri Pazienti</h2>
  </section>
</template>

<script>
export default {
  name: 'Reviews',

  data() {
    return {}
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#reviews {
  border-top: 5px solid rgb(173, 216, 230);
  margin: 25px 40px;
  #reviews-container {
    margin: 30px 0;
  }
  #title-reviews {
    text-align: center;
  }
}
</style>
