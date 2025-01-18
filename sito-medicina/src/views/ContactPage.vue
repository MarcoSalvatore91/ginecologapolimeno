<template>
  <div>
    <Menu />
    <ContactHeader />
    <ContactMain />
    <Footer />
  </div>
</template>

<script>
import Menu from '../components/Menu/Menu.vue'
import ContactHeader from '../components/Contacts/ContactHeader.vue'
import ContactMain from '../components/Contacts/ContactMain.vue'
import Footer from '../components/Footer/Footer.vue'
export default {
  name: 'ContactPage',

  components: {
    Menu,
    ContactHeader,
    ContactMain,
    Footer
  }
}
</script>

<style scoped lang="scss"></style>
