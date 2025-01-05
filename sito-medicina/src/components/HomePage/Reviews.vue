<template>
  <section id="reviews">
    <div id="info-review">
      <div id="reviews-container"></div>
      <h2 id="title-reviews">Recensioni Dei Nostri Pazienti</h2>
    </div>

    <Carousel>
      <Slide v-for="review in reviews" :key="review">
        <div class="carousel__item">
          <div>
            <h3>{{ review.name }}</h3>
            <b-icon-star-fill v-for="star in 5" :key="star"></b-icon-star-fill>
          </div>
          <div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae
            asperiores impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur.
            Assumenda aperiam neque inventore porro laborum itaque!
          </div>
        </div>
      </Slide>

      <template #addons>
        <Pagination />
      </template>
    </Carousel>
  </section>
</template>

<script>
import { Carousel, Navigation, Pagination, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

export default {
  name: 'Reviews',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation
  },

  data() {
    return {
      reviews: [
        {
          name: 'User',
          stars: 5,
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae asperiores impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur. Assumenda aperiam neque inventore porro laborum itaque!'
        },
        {
          name: 'User',
          stars: 5,
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae asperiores impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur. Assumenda aperiam neque inventore porro laborum itaque!'
        },
        {
          name: 'User',
          stars: 5,
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae asperiores impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur. Assumenda aperiam neque inventore porro laborum itaque!'
        },
        {
          name: 'User',
          stars: 5,
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae asperiores impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur. Assumenda aperiam neque inventore porro laborum itaque!'
        },
        {
          name: 'User',
          stars: 5,
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae asperiores impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur. Assumenda aperiam neque inventore porro laborum itaque!'
        }
      ]
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#reviews {
  margin-top: 50px;
  #info-review {
    border-top: 5px solid #fdc8eb66;
    margin: 25px 40px;
    #reviews-container {
      margin: 30px 0;
    }
    #title-reviews {
      text-align: center;
      padding-bottom: 10px;
    }
  }
  .carousel__item {
    min-height: 200px;
    width: 100%;
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.15);
    border-radius: 5px;
    color: black;
    font-size: 20px;
    border-radius: 8px;
    text-align: start;
    padding: 10px 20px;
    div:first-child {
      padding: 20px 0;
      border-bottom: 1px solid #fdc8eb66;
    }
    div:nth-child(2) {
      padding: 20px 0;
    }
  }

  .carousel__slide {
    padding: 10px 20px;
  }

  .carousel__prev,
  .carousel__next {
    box-sizing: content-box;
    border: 5px solid white;
  }
}
</style>
