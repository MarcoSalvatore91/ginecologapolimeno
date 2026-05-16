<template>
  <section id="jumbotron" :style="{ backgroundImage: `url(${tracyImage})` }">
    <div class="jumbotron-overlay" />
    <div id="container-image">
      <h2 class="content-container-image">Dr. Teresa Polimeno</h2>
      <h3 class="content-container-image">Specialista in Ginecologia e Ostetricia</h3>
      <p class="content-container-image tagline">
        “Ogni donna merita un luogo in cui sentirsi compresa, protetta e accompagnata nella propria
        salute.”
      </p>
    </div>
  </section>
</template>

<script>
import tracyImage from '@/assets/images/jumbotron-new.jpeg'

export default {
  name: 'Jumbotron',

  data() {
    return {
      tracyImage
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
#jumbotron {
  position: relative;
  background-color: #e8e8e8;
  background-size: cover;
  background-position: center 30%;
  background-repeat: no-repeat;
  color: white;
  min-height: 320px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.jumbotron-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(0, 0, 0, 0.6) 0%,
    rgba(0, 0, 0, 0.4) 50%,
    rgba(0, 0, 0, 0.55) 100%
  );
  pointer-events: none;
}

#container-image {
  position: relative;
  z-index: 1;
  padding: 40px 24px;
  max-width: 700px;
}

@media (max-width: 480px) {
  #jumbotron {
    min-height: 280px;
  }
  #container-image {
    padding: 32px 16px;
  }
  .content-container-image:first-child {
    font-size: 1.5rem;
  }
  .content-container-image:nth-child(2) {
    font-size: 1rem;
  }
  .content-container-image.tagline {
    font-size: 0.9rem;
  }
}

.content-container-image {
  margin: 0;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
}

.content-container-image:first-child {
  font-size: 1.75rem;
  font-weight: 700;
  margin-bottom: 8px;
  letter-spacing: -0.02em;
}

.content-container-image:nth-child(2) {
  font-size: 1.1rem;
  font-weight: 500;
  margin-bottom: 16px;
  opacity: 0.98;
}

.content-container-image.tagline {
  font-size: 0.95rem;
  font-style: italic;
  opacity: 0.92;
  line-height: 1.5;
}

@media only screen and (min-width: 769px) {
  #jumbotron {
    min-height: 700px;
    align-items: center;
    justify-content: flex-start;
  }

  #container-image {
    padding: 0 0 0 80px;
    max-width: 560px;
    text-align: left;
  }

  .content-container-image:first-child {
    font-size: 2.75rem;
    font-weight: 700;
    margin-bottom: 12px;
    line-height: 1.15;
  }

  .content-container-image:nth-child(2) {
    font-size: 1.25rem;
    margin-bottom: 20px;
  }

  .content-container-image.tagline {
    font-size: 1.05rem;
    letter-spacing: 0.01em;
  }
}
</style>
