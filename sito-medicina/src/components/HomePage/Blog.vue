<template>
  <section id="blog">
    <h2 id="title">Blog e News</h2>
    <p id="text-blog">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit minus et saepe vitae asperiores
      impedit doloribus fuga labore nihil beatae! Pariatur, sint aspernatur. Assumenda aperiam neque
      inventore porro laborum itaque!
    </p>
    <div id="article-section">
      <div class="content-article" v-for="blog in blogList" :key="blog">
        <div class="image-article"></div>
        <div class="info-article">
          <h3 class="title-article">{{ blog.title }}</h3>
          <p class="text-article">{{ blog.content }}</p>
          <p class="router-article">CONTINUA A LEGGERE</p>
        </div>
      </div>
    </div>
    <div id="container-btn-article">
      <button class="router-btn">Scopri tutti gli articoli</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Blog',

  data() {
    return {
      blogList: [
        {
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore quae quos, tempore at eos asperiores illum sed, dolor labore dolorum mollitia ipsam aspernatur, nobis neque! Avoluptas architecto sed error.'
        },
        {
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore quae quos, tempore at eos asperiores illum sed, dolor labore dolorum mollitia ipsam aspernatur, nobis neque! Avoluptas architecto sed error.'
        }
      ]
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#blog {
  margin-top: 50px;
  padding: 0 30px;
  #title {
    text-align: center;
    padding-bottom: 10px;
  }
  #text-blog {
    text-align: center;
  }
  .content-article {
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.15);
    border-radius: 5px;
    .image-article {
      margin: 30px 0;
      height: 150px;
      border-radius: 5px 5px 0 0;
      background-color: lightgrey;
    }
    .info-article {
      padding: 0 30px;
      .text-article {
        margin: 15px 0;
      }
      .router-article {
        font-weight: 900;
        color: rgb(173, 216, 230);
        padding-bottom: 15px;
        cursor: pointer;
      }
    }
  }
  #container-btn-article {
    margin: 50px 0;
    display: flex;
    justify-content: center;
  }
}
@media only screen and (min-width: 769px) {
  #blog {
    #text-blog {
      margin-bottom: 50px;
      text-align: left;
      margin-left: 20px;
    }
    #article-section {
      display: flex;
      .content-article {
        margin: 0 20px;
        .image-article {
          margin-top: 0;
          margin-bottom: 20px;
        }
      }
    }
  }
}
</style>
