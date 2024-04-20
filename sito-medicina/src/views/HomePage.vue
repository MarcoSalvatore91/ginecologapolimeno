<template>
  <section id="homepage">
    <Menu />
    <Jumbotron />
    <Contacts />
    <Visits />
    <Biography />
    <Blog />
    <Reviews />
  </section>
</template>

<script>
import Menu from '../components/Menu/Menu.vue'
import Jumbotron from '../components/HomePage/Jumbotron.vue'
import Contacts from '../components/HomePage/Contacts.vue'
import Visits from '../components/HomePage/Visits.vue'
import Biography from '../components/HomePage/Biography.vue'
import Blog from '../components/HomePage/Blog.vue'
import Reviews from '../components/HomePage/Reviews.vue'

export default {
  name: 'HomePage',

  components: {
    Menu,
    Jumbotron,
    Contacts,
    Visits,
    Biography,
    Blog,
    Reviews
  }
}
</script>

<style scoped lang="scss"></style>
