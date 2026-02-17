<template>
  <section id="homepage" class="homepage-wrap">
    <Menu />
    <Jumbotron />
    <Contacts />
    <Visits />
    <Biography />
    <section class="reviews-block">
      <h2 class="block-title">Recensioni Dei Nostri Pazienti</h2>
      <div class="reviews-inner">
        <Reviews />
      </div>
    </section>
    <Footer />
  </section>
</template>

<script>
import Menu from '../components/Menu/Menu.vue'
import Footer from '../components/Footer/Footer.vue'
import Jumbotron from '../components/HomePage/Jumbotron.vue'
import Contacts from '../components/HomePage/Contacts.vue'
import Visits from '../components/HomePage/Visits.vue'
import Biography from '../components/HomePage/Biography.vue'
/* import Blog from '../components/HomePage/Blog.vue' */
import Reviews from '../components/HomePage/Reviews.vue'

export default {
  name: 'HomePage',

  components: {
    Menu,
    Jumbotron,
    Contacts,
    Visits,
    Biography,
    /* Blog, */
    Reviews,
    Footer
  }
}
</script>

<style scoped lang="scss">
.homepage-wrap {
  background: #f8f8f8;
}

.reviews-block {
  padding: 48px 20px 64px;
  background: #f8f8f8;
}

.block-title {
  text-align: center;
  font-size: 1.75rem;
  font-weight: 700;
  color: #2c2c2c;
  margin-bottom: 36px;
  letter-spacing: -0.02em;
}

.reviews-inner {
  max-width: 900px;
  margin: 0 auto;
}

@media only screen and (min-width: 769px) {
  .reviews-block {
    padding: 64px 40px 80px;
  }

  .block-title {
    font-size: 2rem;
    margin-bottom: 44px;
  }
}
</style>
