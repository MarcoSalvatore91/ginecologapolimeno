<template>
  <section id="biography">
    <div
      id="content-biography"
      :class="{ 'biography-mobile-overlay-visible': overlayVisible }"
      @click="onMobileCardClick"
    >
      <div id="image-biography" ref="imageCol" :style="imageHeightStyle">
        <img src="@/assets/images/foto-biography-clean.png" alt="Dott.ssa Teresa Polimeno" />
      </div>
      <div id="text-biography" ref="textCol" @click.stop>
        <h2>Dott.ssa Teresa Polimeno</h2>
        <p>
          Laureata con Lode e Menzione alla Carriera presso l'Università degli Studi di Firenze e
          Specializzata con Lode all'Università Cattolica del Sacro Cuore – Fondazione Policlinico
          A. Gemelli, mi dedico con passione alla Diagnostica Ecografica Ginecologica e Ostetrica.
        </p>
        <p>
          Sono certificata dalla Fetal Medicine Foundation di Londra per l'esecuzione del Bitest e
          svolgo ecografie ostetriche in tutti i trimestri di gravidanza: premorfologiche,
          morfologiche e di III trimestre con flussimetria fetale, offrendo un monitoraggio completo
          e accurato del benessere materno-fetale.
        </p>
        <p>
          Esperta in patologia ostetrica, seguo sia gravidanze fisiologiche sia gravidanze a
          rischio, integrando competenza clinica ed ecografica per un'assistenza personalizzata e
          attenta. Mi occupo inoltre di Ginecologia Disfunzionale, con particolare interesse per
          irregolarità mestruali (amenorrea, polimenorrea, dismenorrea) e Sindrome dell’Ovaio
          Policistico, guidando la paziente verso la terapia più adeguata.
        </p>
        <p>
          Completa la mia attività l'esperienza nella gestione di sterilità di coppia e abortività
          ricorrente, accompagnando la donna e la coppia in un percorso di cura sensibile e
          competente.
        </p>
        <p class="signature">Dott.ssa Teresa Polimeno</p>
      </div>
      <div v-if="isMobile" class="biography-mobile-hint" aria-hidden="true">
        <span>Tocca per leggere la biografia</span>
      </div>
      <button
        v-if="isMobile && overlayVisible"
        type="button"
        class="biography-mobile-close"
        aria-label="Chiudi"
        @click.stop="overlayVisible = false"
      >
        <svg
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          width="20"
          height="20"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2.5"
          stroke-linecap="round"
        >
          <path d="M18 6L6 18M6 6l12 12" />
        </svg>
      </button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Biography',

  data() {
    return {
      imageHeightStyle: {},
      overlayVisible: false,
      isMobile: false
    }
  },

  mounted() {
    this.checkMobile()
    this.matchImageToTextHeight()
    window.addEventListener('resize', this.matchImageToTextHeight)
    window.addEventListener('resize', this.checkMobile)
    setTimeout(this.matchImageToTextHeight, 100)
  },

  beforeUnmount() {
    window.removeEventListener('resize', this.matchImageToTextHeight)
    window.removeEventListener('resize', this.checkMobile)
  },

  methods: {
    checkMobile() {
      this.isMobile = window.innerWidth <= 768
      if (!this.isMobile) this.overlayVisible = false
    },
    onMobileCardClick() {
      if (window.innerWidth > 768) return
      this.overlayVisible = !this.overlayVisible
    },
    matchImageToTextHeight() {
      this.$nextTick(() => {
        const textCol = this.$refs.textCol
        const imageCol = this.$refs.imageCol
        if (!textCol || !imageCol || window.innerWidth < 769) {
          this.imageHeightStyle = {}
          return
        }
        const textHeight = textCol.offsetHeight
        this.imageHeightStyle = { height: `${textHeight}px` }
      })
    }
  }
}
</script>

<style scoped lang="scss">
$accent: #a6d1e8;

#biography {
  padding: 0 20px 48px;
  #content-biography {
    #image-biography {
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
      img {
        width: 100%;
        height: auto;
        display: block;
        object-fit: cover;
      }
    }
    #text-biography {
      h2 {
        font-size: 1.5rem;
        color: #2c2c2c;
        margin-bottom: 16px;
      }
      p {
        color: #555;
        font-size: 0.95rem;
        line-height: 1.7;
        margin-bottom: 12px;
      }
      .signature {
        margin-top: 20px;
        font-style: italic;
        color: $accent;
        font-size: 1rem;
      }
    }
  }
}

@media (max-width: 480px) {
  #biography {
    padding: 0 16px 40px;
  }
  #biography #text-biography p {
    font-size: 1rem;
    line-height: 1.65;
  }
  #biography #text-biography h2 {
    font-size: 1.35rem;
  }
}

/* Mobile: testo nascosto, appare sopra immagine con overlay e opacity */
@media (max-width: 768px) {
  #biography #content-biography {
    position: relative;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
    cursor: pointer;
    aspect-ratio: 4 / 5;
  }
  #biography #image-biography {
    position: absolute;
    inset: 0;
    margin: 0;

    &::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(
        to bottom,
        transparent 0%,
        transparent 72%,
        rgba(0, 0, 0, 0.25) 88%,
        rgba(0, 0, 0, 0.7) 100%
      );
      pointer-events: none;
    }
  }
  #biography #image-biography img {
    width: 100%;
    height: 100%;
    display: block;
    object-fit: cover;
    object-position: center center;
  }
  #biography #content-biography #text-biography {
    position: absolute;
    inset: 0;
    background: linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0.55) 0%,
      rgba(0, 0, 0, 0.72) 50%,
      rgba(0, 0, 0, 0.85) 100%
    );
    color: #ffffff !important;
    padding: 28px 20px 56px;
    overflow-y: auto;
    -webkit-overflow-scrolling: touch;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.35s ease;
    display: flex;
    flex-direction: column;
  }
  #biography #content-biography #text-biography h2 {
    color: #ffffff !important;
    margin-bottom: 14px;
    font-weight: 700;
    text-shadow:
      0 1px 4px #000,
      0 0 10px rgba(0, 0, 0, 0.95);
  }
  #biography #content-biography #text-biography p {
    color: #ffffff !important;
    margin-bottom: 12px;
    font-size: 1.05rem;
    line-height: 1.7;
    text-shadow:
      0 1px 4px #000,
      0 0 10px rgba(0, 0, 0, 0.95);
  }
  #biography #content-biography #text-biography .signature {
    color: #e8c4e0 !important;
    margin-top: 16px;
    font-weight: 600;
    text-shadow: 0 1px 3px #000;
  }
  #biography #content-biography.biography-mobile-overlay-visible #text-biography {
    opacity: 1;
    pointer-events: auto;
  }
  #biography #content-biography.biography-mobile-overlay-visible {
    cursor: default;
  }
  .biography-mobile-hint {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 14px 16px;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.75), transparent);
    text-align: center;
    pointer-events: none;
  }
  .biography-mobile-hint span {
    font-size: 1.1rem;
    color: rgba(255, 255, 255, 0.95);
    font-weight: 500;
  }
  #biography #content-biography.biography-mobile-overlay-visible .biography-mobile-hint {
    display: none;
  }
  .biography-mobile-close {
    position: absolute;
    top: 12px;
    right: 12px;
    z-index: 2;
    width: 40px;
    height: 40px;
    border: none;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.25);
    color: #fff;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
    box-sizing: border-box;
  }
  .biography-mobile-close svg {
    display: block;
  }
}

@media only screen and (min-width: 769px) {
  #biography {
    background: linear-gradient(to bottom, #fcfcfc 0%, #fff 100%);
    border-radius: 0;
    overflow: hidden;
  }

  #biography #content-biography {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    gap: 0;
    max-width: 1400px;
    margin: 0 auto;
    padding: 48px 32px;
    min-height: 420px;

    /* Altezza foto impostata via JS per coincidere con il testo */
    #image-biography {
      flex: 0 0 40%;
      margin: 0;
      border-radius: 12px 0 0 12px;
      overflow: hidden;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
      display: flex;
      align-items: center;
      justify-content: center;
      background: #f7f7f7;
      img {
        width: 100%;
        height: 100%;
        max-height: 100%;
        display: block;
        object-fit: contain;
        object-position: center center;
      }
    }

    #text-biography {
      flex: 1;
      padding: 44px 52px 48px 44px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      border-left: 3px solid rgba($accent, 0.2);
      background: white;
      box-shadow: 0 4px 24px rgba(0, 0, 0, 0.04);

      h2 {
        font-size: 1.75rem;
        color: #2c2c2c;
        margin-bottom: 22px;
        font-weight: 700;
        letter-spacing: -0.02em;
      }
      p {
        font-size: 0.9375rem;
        line-height: 1.78;
        margin-bottom: 14px;
        color: #444;
      }
      .signature {
        margin-top: 24px;
        font-size: 1.05rem;
        font-weight: 500;
      }
    }
  }
}
</style>
