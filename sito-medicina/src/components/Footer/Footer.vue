<template>
  <section id="footer">
    <div id="content-footer">
      <div class="info">
        <h4>DR. TERESA POLIMENO</h4>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
      </div>
      <div class="info">
        <h4>INFO</h4>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
      </div>
      <div id="text-footer">
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
  name: 'Footer',

  data() {
    return {}
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#footer {
  margin-top: 50px;
  background-color: rgb(85, 91, 100);
  #content-footer {
    padding: 30px;
    .info {
      margin: 30px 0 50px 0;
      height: 200px;
      h4 {
        color: #fdc8eb66;
      }
      p {
        color: white;
      }
    }
    #text-footer {
      margin-bottom: 30px;
    }
  }
}
@media only screen and (min-width: 769px) {
  #footer {
    margin-top: 80px;
    #content-footer {
      display: flex;
      padding: 30px 150px;
      .info {
        width: 50%;
        height: 300px;
        margin: 10px 20px;
      }
      #text-footer {
        width: 50%;
        margin: 10px 20px;
      }
    }
  }
}
</style>
