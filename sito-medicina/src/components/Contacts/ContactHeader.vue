<template>
  <header id="contact-header">
    <div class="contact-header-inner">
      <h1 class="contact-header-title">Prenota una visita o contattaci per avere maggiori informazioni</h1>
    </div>
  </header>
</template>

<script>
export default {
  name: 'ContactHeader',

  components: {}
}
</script>

<style scoped lang="scss">
$accent: #d97cb1;

#contact-header {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 180px;
  padding: 48px 24px;
  background: rgba($accent, 0.08);
}

.contact-header-inner {
  max-width: 1200px;
  width: 100%;
  text-align: center;
}

.contact-header-title {
  margin: 0;
  font-size: 1.5rem;
  font-weight: 700;
  color: #2c2c2c;
  letter-spacing: -0.02em;
  line-height: 1.3;
}

@media only screen and (min-width: 769px) {
  #contact-header {
    min-height: 200px;
    padding: 56px 40px;
  }

  .contact-header-title {
    font-size: 1.75rem;
  }
}
</style>
