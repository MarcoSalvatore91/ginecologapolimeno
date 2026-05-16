<template>
  <section class="contacts-section">
    <div class="contacts-wrapper">
      <div class="contact-card">
        <div class="contact-card-header">
          <b-icon-geo-alt-fill class="contact-icon" />
          <h3 class="contact-title">Ricevo presso</h3>
        </div>
        <div class="contact-card-list">
          <div class="location-block">
            <p class="location-name">Ospedale Cristo Re</p>
            <p class="contact-detail">Via delle Calasanziane 25, 00167 Roma</p>
          </div>
          <div class="location-block">
            <p class="location-name">Studio Medico Trionfale</p>
            <p class="contact-detail">Via Trionfale 5367, 00132 Roma</p>
          </div>
          <div class="location-block">
            <p class="location-name">Mizar Studio Specialistico</p>
            <p class="contact-detail">Via Fosso dell'Osa 603/605, 00132 Roma</p>
          </div>
        </div>
      </div>
      <div class="contact-card">
        <div class="contact-card-header">
          <b-icon-envelope-fill class="contact-icon" />
          <h3 class="contact-title">Contatti</h3>
        </div>
        <div class="contact-card-list">
          <div class="contact-line">
            <span class="contact-label">Ospedale Cristo Re</span>
            <a href="tel:+3906612451">+39 066 12451</a>
          </div>
          <div class="contact-line">
            <span class="contact-label">Ospedale Cristo Re</span>
            <a href="tel:+393457958164">+39 345 7958164</a>
          </div>
          <div class="contact-line">
            <span class="contact-label">Mizar</span>
            <a href="tel:+390659879859">+39 065 9879859</a>
          </div>
        </div>
      </div>
      <div class="contact-card">
        <div class="contact-card-header">
          <b-icon-telephone-fill class="contact-icon" />
          <h3 class="contact-title">Contatti personali</h3>
        </div>
        <div class="contact-card-list">
          <div class="contact-line">
            <span class="contact-label">Telefono</span>
            <a href="tel:3514959696">351 495 9696</a>
          </div>
          <div class="contact-line">
            <span class="contact-label">Email</span>
            <a href="mailto:teresapolimeno.ginecologia@outlook.it"
              >teresapolimeno.ginecologia@outlook.it</a
            >
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contacts',

  data() {
    return {}
  },

  methods: {}
}
</script>

<style scoped lang="scss">
$accent: #a6d1e8;

.contacts-section {
  padding: 0 20px 48px;
  margin-top: -52px;
  position: relative;
  z-index: 2;
}

@media (max-width: 480px) {
  .contacts-section {
    padding: 0 16px 40px;
  }
  .contact-card {
    padding: 20px 18px;
    min-height: auto;
  }
  .contact-line {
    min-height: 44px;
  }
  .contact-line a {
    padding: 4px 0;
  }
}

.contacts-wrapper {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.contact-card {
  display: flex;
  flex-direction: column;
  background: white;
  border-radius: 16px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
  padding: 18px 24px;
  min-height: 200px;
  transition: box-shadow 0.25s ease;

  h3,
  p,
  .contact-line > * {
    margin: 0;
    padding: 0;
  }
  .contact-card-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
  }
  .contact-icon {
    width: 28px;
    height: 28px;
    color: $accent;
    margin: 0;
    display: block;
  }
  .contact-title {
    color: #2c2c2c;
    font-size: 1rem;
    font-weight: 700;
    margin: 0;
    letter-spacing: 0.02em;
    flex-shrink: 0;
  }
  .contact-card-list {
    flex: 1;
    display: flex;
    flex-direction: column;
    min-height: 0;
  }
  .contact-detail,
  .contact-meta {
    color: #555;
    font-size: 0.9rem;
    line-height: 1.3;
  }
  .location-block,
  .contact-line {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-bottom: 10px;
    margin-bottom: 10px;
    border-bottom: 1px solid #f3f3f3;
    line-height: 1.3;
    &:last-child {
      margin-bottom: 0;
      padding-bottom: 0;
      border-bottom: none;
    }
  }
  .contact-line {
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    gap: 8px;
  }
  .location-name {
    font-weight: 600;
    color: #2c2c2c;
    font-size: 0.95rem;
    margin: 0 0 1px 0;
  }
  .contact-label {
    flex: 0 0 auto;
    font-weight: 600;
    color: #2c2c2c;
    font-size: 0.875rem;
  }
  a {
    color: #2c2c2c;
    text-decoration: none;
    font-size: 0.9rem;
    display: inline;
    line-height: 1.3;
  }
  a:hover {
    color: $accent;
  }
}

@media only screen and (min-width: 769px) {
  .contacts-section {
    margin-top: -72px;
    padding: 0 40px 64px;
  }

  .contacts-wrapper {
    flex-direction: row;
    gap: 24px;
    align-items: flex-start;
  }

  .contact-card {
    flex: 1;
    padding: 22px 28px;
    min-height: 250px;

    &:hover {
      box-shadow: 0 12px 40px rgba(0, 0, 0, 0.1);
    }
  }

  .contact-label {
    flex: 0 0 100px;
    font-size: 0.85rem;
  }
}
</style>
