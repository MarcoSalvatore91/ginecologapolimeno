<template>
  <section id="biography">
    <div id="content-biography">
      <div id="image-biography"></div>
      <div id="text-biography">
        <h2>Dr. Teresa Polimeno</h2>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Nisi at sunt praesentium, cum
          magnam suscipit. Saepe, nesciunt. A dolorem totam, reprehenderit id culpa quas itaque
          illum quam, aliquid provident soluta.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Biography',

  data() {
    return {}
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#biography {
  margin-top: 50px;
  background-color: lightgrey;
  #content-biography {
    padding: 30px;
    #image-biography {
      margin: 30px 0;
      height: 200px;
      background-color: rgb(173, 216, 230);
    }
    #text-biography {
      margin-bottom: 30px;
    }
  }
}
</style>
