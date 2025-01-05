<template>
  <section id="visits">
    <h1>Prestazioni Eseguite</h1>
    <div id="visits-field-container">
      <div class="visit-field" v-for="visit in visitList" :key="visit">
        <div class="container-image"></div>
        <h3 class="title-visit">{{ visit.title }}</h3>
        <p class="text-visit">
          {{ visit.content }}
        </p>
        <!-- <div class="btn-container">
          <button class="router-btn">Scopri di più</button>
        </div> -->
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Visits',

  data() {
    return {
      visitList: [
        {
          title: 'Visita Ginecologica',
          content:
            'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quisquam, omnis accusantium pariatur.'
        },
        {
          title: 'Ecografia Pelvica',
          content:
            'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quisquam, omnis accusantium pariatur.'
        },
        {
          title: 'Ecografia Ostetrica',
          content:
            'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quisquam, omnis accusantium pariatur.'
        },
        {
          title: 'Test Combinato',
          content:
            'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quisquam, omnis accusantium pariatur.'
        }
      ]
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
$main-color: #fdc8eb66;

#visits {
  margin: 0 20px;
  h1 {
    text-align: center;
    border-bottom: 3px solid $main-color;
    margin: 50px 30px 20px 30px;
  }
  .visit-field {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .container-image {
      margin-top: 70px;
      height: 100px;
      width: 100px;
      border-radius: 50px;
      background-color: $main-color;
    }
    .title-visit {
      color: $main-color;
      padding: 15px 0;
    }
    .text-visit {
      text-align: center;
    }
    .btn-container {
      padding-top: 15px;
    }
  }
}

@media only screen and (min-width: 769px) {
  .hidden {
    display: none;
  }
  #visits {
    h1 {
      border-bottom: 0;
    }
    #visits-field-container {
      display: flex;
    }
  }
}
</style>
