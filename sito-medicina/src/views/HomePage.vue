<template>
  <section id="homepage">
    <Menu id="menu" />
    <Jumbotron />
    <Contacts />
    <Visits />
  </section>
</template>

<script>
import Menu from '../components/Menu/Menu.vue'
import Jumbotron from '../components/HomePage/Jumbotron.vue'
import Contacts from '../components/HomePage/Contacts.vue'
import Visits from '../components/HomePage/Visits.vue'

export default {
  name: 'HomePage',

  components: {
    Menu,
    Jumbotron,
    Contacts,
    Visits
  }
}
</script>

<style scoped lang="scss">
#menu {
}
</style>
