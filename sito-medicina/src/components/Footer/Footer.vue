<template>
  <footer id="footer">
    <div id="content-footer">
      <div class="footer-col footer-brand">
        <div class="logo-footer">
          <img :src="logoImg" alt="Dr. Teresa Polimeno" class="logo-img" />
          <div class="logo-text-wrap">
            <span class="logo-name">Dott.ssa Teresa</span>
            <span class="logo-surname">Polimeno</span>
          </div>
        </div>
        <p class="copyright">
          © {{ new Date().getFullYear() }} Dr. Teresa Polimeno. Tutti i diritti riservati.
        </p>
      </div>
      <div class="footer-col">
        <h4>INFO</h4>
        <p>
          Specialista in Ginecologia e Ostetricia. Ricevo presso Ospedale Cristo Re e Mizar Medicina
          Specialistica a Roma.
        </p>
      </div>
      <div class="footer-col">
        <h4>SERVIZI</h4>
        <p>
          Visita ginecologica, ecografia pelvica e ostetrica, gravidanza, test combinato e NIPT.
        </p>
      </div>
      <div class="footer-col">
        <h4>CONTATTI</h4>
        <p>
          <a href="https://ospedalecristore.it" target="_blank" rel="noopener noreferrer"
            >Ospedale Cristo Re</a
          >
        </p>
        <p>
          <a href="tel:3514959696">351 495 9696</a> ·
          <a href="mailto:teresapolimeno.ginecologia@outlook.it">Email</a>
        </p>
        <div class="social-links">
          <a href="#" aria-label="LinkedIn" class="social-icon">in</a>
          <a href="#" aria-label="Instagram" class="social-icon">ig</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import logoImg from '@/assets/images/logo.svg'

export default {
  name: 'Footer',

  data() {
    return {
      logoImg
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
$accent: #a6d1e8;

#footer {
  margin-top: 0;
  background-color: #2e3238;
  color: #e4e4e4;
  padding: 56px 24px 40px;
}

#content-footer {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr;
  gap: 36px;
}

.footer-col {
  h4 {
    color: $accent;
    font-size: 0.85rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-bottom: 14px;
  }
  p {
    font-size: 0.9rem;
    line-height: 1.65;
    color: #b8bcc4;
    margin: 0 0 10px;
  }
  a {
    color: #b8bcc4;
    text-decoration: none;
    transition: color 0.2s;
  }
  a:hover {
    color: $accent;
  }
}

.footer-brand {
  .logo-footer {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 14px;
  }
  .logo-img {
    height: 42px;
    width: auto;
    display: block;
    flex-shrink: 0;
  }
  .logo-text-wrap {
    display: flex;
    flex-direction: column;
    gap: 2px;
    line-height: 1.2;
  }
  .logo-name {
    font-size: 0.95rem;
    font-weight: 600;
    font-style: italic;
    color: $accent;
  }
  .logo-surname {
    font-size: 1.05rem;
    font-weight: 600;
    font-style: italic;
    color: $accent;
    letter-spacing: 0.02em;
  }
  .copyright {
    font-size: 0.8rem;
    color: #7a7e86;
    line-height: 1.5;
  }
}

.social-links {
  display: flex;
  gap: 12px;
  margin-top: 12px;
  .social-icon {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.1);
    color: #c0c0c0;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.85rem;
    font-weight: 600;
  }
  .social-icon:hover {
    background: $accent;
    color: white;
  }
}

@media (max-width: 480px) {
  #footer {
    padding: 40px 16px 32px;
  }
  .social-links .social-icon {
    width: 44px;
    height: 44px;
  }
  .footer-col p,
  .footer-col a {
    font-size: 0.9375rem;
  }
}

@media only screen and (min-width: 600px) {
  #content-footer {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media only screen and (min-width: 960px) {
  #footer {
    padding: 64px 40px 48px;
  }

  #content-footer {
    grid-template-columns: 1.2fr 1fr 1fr 1fr;
    gap: 48px;
    padding: 0;
  }
}
</style>
