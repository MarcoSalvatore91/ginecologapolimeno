<template>
  <section id="biography">
    <div id="content-biography">
      <div id="image-biography" ref="imageCol" :style="imageHeightStyle">
        <img src="@/assets/images/tracy_2.jpeg" alt="Dr. Teresa Polimeno" />
      </div>
      <div id="text-biography" ref="textCol">
        <h2>Dr. Teresa Polimeno</h2>
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
          attenta. Mi occupo inoltre di Ginecologia Disfunzionale, con particolare interesse per irregolarità mestruali (amenorrea,
          polimenorrea, dismenorrea) e Sindrome dell’Ovaio Policistico, guidando la paziente verso la terapia più adeguata.
        </p>
        <p>
          Completa la mia attività l'esperienza nella gestione di sterilità di coppia e abortività
          ricorrente, accompagnando la donna e la coppia in un percorso di cura sensibile e
          competente.
        </p>
        <p class="signature">Dr. Teresa Polimeno</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Biography',

  data() {
    return {
      imageHeightStyle: {}
    }
  },

  mounted() {
    this.matchImageToTextHeight()
    window.addEventListener('resize', this.matchImageToTextHeight)
    // Riprova dopo il layout (font, immagini)
    setTimeout(this.matchImageToTextHeight, 100)
  },

  beforeUnmount() {
    window.removeEventListener('resize', this.matchImageToTextHeight)
  },

  methods: {
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
$accent: #d97cb1;

#biography {
  #content-biography {
    #image-biography {
      margin: 0 0 20px;
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
