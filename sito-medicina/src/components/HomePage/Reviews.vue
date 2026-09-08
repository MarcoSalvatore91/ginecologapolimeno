<template>
  <section id="reviews" class="reviews-wrap">
    <Carousel :wrap-around="true">
      <Slide v-for="(review, index) in reviews" :key="`${review.name}-${index}`">
        <div
          class="carousel__item"
          :class="{ 'carousel__item--clickable': isMobile }"
          @click="isMobile ? openModal(review) : null"
        >
          <div class="review-header">
            <h3>{{ review.name }}</h3>
            <div class="stars-row">
              <b-icon-star-fill v-for="star in 5" :key="star" />
            </div>
          </div>
          <div class="review-text">
            {{ isMobile ? truncateWords(review.text, 28) : review.text }}
          </div>
          <div v-if="isMobile && review.text.split(/\s+/).length > 28" class="review-read-more">
            <span class="review-read-more-label">Leggi tutta la recensione</span>
            <b-icon-chevron-down class="review-read-more-icon" />
          </div>
        </div>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>

    <!-- Modal recensione (solo mobile) -->
    <Teleport to="body">
      <Transition name="modal">
        <div v-if="modalReview" class="review-modal-overlay" @click.self="closeModal">
          <div class="review-modal">
            <button
              type="button"
              class="review-modal-close"
              aria-label="Chiudi"
              @click="closeModal"
            >
              <b-icon-x-lg />
            </button>
            <div class="review-modal-header">
              <h3>{{ modalReview.name }}</h3>
              <div class="stars-row">
                <b-icon-star-fill v-for="star in 5" :key="star" />
              </div>
            </div>
            <div class="review-modal-body">
              <p class="review-modal-text">{{ modalReview.text }}</p>
              <div class="review-modal-scroll-hint">
                <b-icon-chevron-down />
                <span>Scorri per leggere</span>
              </div>
            </div>
          </div>
        </div>
      </Transition>
    </Teleport>
  </section>
</template>

<script>
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'
import { BIconStarFill, BIconChevronDown, BIconXLg } from 'bootstrap-icons-vue'

export default {
  name: 'Reviews',
  components: {
    Carousel,
    Slide,
    Navigation,
    BIconStarFill,
    BIconChevronDown,
    BIconXLg
  },

  data() {
    return {
      modalReview: null,
      isMobile: false,
      reviews: [
        {
          name: 'Eleonora',
          stars: 5,
          text: 'A volte le persone più importanti arrivano nella nostra vita quasi per caso, ed è proprio così che ho conosciuto e scelto la mia ginecologa. Una scelta fatta senza sapere quanto sarebbe diventata preziosa per me. Con il tempo ho scoperto non solo una professionista eccezionale, preparata, scrupolosa e attenta, ma soprattutto una persona capace di ascoltare davvero, di comprendere e di trasmettere quella serenità e quella fiducia di cui, in momenti così delicati, si ha un bisogno enorme. Con lei mi sono sempre sentita accolta, capita e mai giudicata. Ha un modo speciale di prendersi cura delle sue pazienti, con una sensibilità e un’umanità che vanno ben oltre la sua straordinaria competenza. È talmente brava nel suo lavoro e talmente speciale come persona che, alla fine, non puoi fare a meno di affezionarti a lei e di volerle bene. Sono davvero grata al caso per avermela fatta incontrare. Oggi non sceglierei nessun’altra.'
        },
        {
          name: 'Martina',
          stars: 5,
          text: 'Consiglio vivamente la Dott.ssa Polimeno! È una ginecologa eccezionale che unisce una professionalità impeccabile a una rara sensibilità umana. Fin dalla prima visita, mi sono sentita completamente a mio agio. È estremamente competente, spiega ogni aspetto in modo chiaro e risponde a qualsiasi domanda con pazienza e accuratezza, dimostrando grande preparazione e attenzione ai dettagli. La sua empatia è ciò che la distingue: è un medico che sa ascoltare davvero, creando un ambiente sereno e di totale fiducia, fondamentale in un ambito così delicato. Inoltre, la sua disponibilità è ammirevole. È sempre raggiungibile e pronta a fornire supporto o chiarimenti, il che è un enorme sollievo e dimostra la sua dedizione alle pazienti.'
        },
        {
          name: 'Anna',
          stars: 5,
          text: 'Empatica, attenta, professionale, precisa, scrupolosa. Una delle migliori dottoresse che io abbia mai conosciuto.'
        },
        {
          name: 'Maria',
          stars: 5,
          text: 'La Dottoressa ha eseguito l ecografia con scrupolosità ed attenzione. La sua grande preparazione specialistica è evidente anche a chi, come noi, non ha conoscenze in medicina. Consiglio vivamente la Dott.ssa Polimeno.'
        },
        {
          name: 'Teresa',
          stars: 5,
          text: 'Mi ha accompagnata per tutta la gravidanza, è stata gentile, preparatissima, chiara e sempre presente. ovviamente rimarrà sempre la mia ginecologa di fiducia.'
        },
        {
          name: 'Claudia',
          stars: 5,
          text: 'Dopo anni sono tornata in uno studio di Ginecologia, avendo avuto una brutta esperienza passata in un consultorio, perché ho scoperto di essere incinta. Il servizio ricevuto è stato eccellente, la Dottoressa è molto empatica e disponibile e spiega le cose in modo dettagliato. Felice di essermi affidata alla dottoressa Polimeno e di aver messo nelle sue mani il bimbo che porto in grembo.'
        },
        {
          name: 'Carmen',
          stars: 5,
          text: "L'Ecografia della translucenza nucale eseguita dalla dottoressa Polimeno è stata molto accurata e dettagliata. La dottoressa è una professionista seria, competente e puntuale. Mi ha colpito anche la sua onestà nel consigliarmi gli esami davvero utili da fare. A livello umano ha dimostrato gentilezza e attenzione."
        },
        {
          name: 'Sonia',
          stars: 5,
          text: 'La dott.ssa Polimeno è una persona professionale, accogliente e davvero gentile. La visita è andata benissimo e sono stata trattata con dignità e non ho provato nessun imbarazzo. Sono lieta che sia diventata la mia dottoressa'
        },
        {
          name: 'Rossana',
          stars: 5,
          text: "Professionista esemplare, chiara ed esaustiva nelle spiegazioni, ottima comunicazione. Dottoressa estremamente avvezza all'empatia e capace di annullare da subito la sensazione di disagio."
        }
      ]
    }
  },

  mounted() {
    this.checkMobile()
    window.addEventListener('resize', this.checkMobile)
  },

  beforeUnmount() {
    window.removeEventListener('resize', this.checkMobile)
  },

  methods: {
    checkMobile() {
      this.isMobile = window.innerWidth <= 480
    },
    truncateWords(text, limit) {
      if (!text) return ''
      const words = text.trim().split(/\s+/)
      if (words.length <= limit) return text
      return words.slice(0, limit).join(' ') + '…'
    },
    openModal(review) {
      this.modalReview = review
      document.body.style.overflow = 'hidden'
    },
    closeModal() {
      this.modalReview = null
      document.body.style.overflow = ''
    }
  }
}
</script>

<style scoped lang="scss">
$accent: #a6d1e8;

.reviews-wrap {
  position: relative;
  padding: 0 28px;
}

.review-read-more {
  display: none;
}
@media (max-width: 480px) {
  .review-read-more {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    margin-top: 14px;
    padding-top: 14px;
    border-top: 1px dashed rgba(0, 0, 0, 0.1);
    color: $accent;
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
  }
  .review-read-more-icon {
    width: 18px;
    height: 18px;
    flex-shrink: 0;
  }
}

@media (max-width: 480px) {
  .reviews-wrap {
    padding: 0 12px;
  }
  #reviews :deep(.carousel__prev) {
    left: 4px;
  }
  #reviews :deep(.carousel__next) {
    right: 4px;
  }
  #reviews .carousel__item {
    padding: 28px 18px 24px;
    min-height: 200px;
    font-size: 1rem;
  }
  #reviews .carousel__item--clickable {
    cursor: pointer;
  }
  #reviews .review-text {
    font-size: 1rem;
    line-height: 1.65;
    padding-top: 16px;
  }
  #reviews .review-header h3 {
    font-size: 1.15rem;
  }
  #reviews :deep(.carousel__prev),
  #reviews :deep(.carousel__next) {
    width: 48px;
    height: 48px;
  }
  #reviews :deep(.carousel__slide) {
    padding: 10px 4px;
  }
}

#reviews :deep(.carousel__prev) {
  left: -40px;
}
#reviews :deep(.carousel__next) {
  right: -40px;
}

#reviews {
  .carousel__item {
    min-height: 220px;
    width: 100%;
    border-radius: 16px;
    color: #2c2c2c;
    font-size: 0.95rem;
    text-align: center;
    padding: 42px 28px 38px;
    background: white;
    border: 1px solid rgba(0, 0, 0, 0.06);
    border-left: 4px solid $accent;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.3s ease;
  }

  .carousel__item:hover {
    box-shadow: 0 8px 28px rgba(0, 0, 0, 0.08);
  }

  .review-header {
    padding: 0 0 20px;
    border-bottom: 2px solid rgba($accent, 0.2);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
    h3 {
      font-size: 1.28rem;
      font-weight: 700;
      color: $accent;
      margin: 0;
      letter-spacing: -0.02em;
    }
  }

  .stars-row {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 5px;
  }

  .stars-row :deep(.b-icon),
  .stars-row :deep(svg),
  .stars-row :deep(path) {
    color: $accent;
    fill: $accent;
    width: 22px;
    height: 22px;
  }

  .review-text {
    padding: 24px 0 0;
    line-height: 1.72;
    color: #555;
    text-align: left;
    font-size: 0.9375rem;
  }

  .carousel__slide {
    padding: 14px 24px;
  }

  .carousel__prev,
  .carousel__next {
    box-sizing: content-box;
    border: none;
    color: white;
    background: $accent;
    width: 46px;
    height: 46px;
    border-radius: 50%;
    transition:
      background 0.25s ease,
      transform 0.25s ease,
      box-shadow 0.25s ease;
    box-shadow: 0 2px 12px rgba(188, 141, 183, 0.35);
  }
  .carousel__prev:hover,
  .carousel__next:hover {
    background: darken($accent, 10%);
    transform: scale(1.08);
    box-shadow: 0 4px 16px rgba(188, 141, 183, 0.4);
  }
}

/* Modal recensione (mobile) */
.review-modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  box-sizing: border-box;
}
.review-modal {
  background: white;
  border-radius: 16px;
  max-width: 420px;
  width: 100%;
  max-height: 85vh;
  display: flex;
  flex-direction: column;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
  position: relative;
}
.review-modal-close {
  position: absolute;
  top: 12px;
  right: 12px;
  width: 40px;
  height: 40px;
  border: none;
  background: rgba(0, 0, 0, 0.06);
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #2c2c2c;
  z-index: 2;
}
.review-modal-close :deep(svg) {
  width: 20px;
  height: 20px;
}
.review-modal-header {
  padding: 24px 24px 16px;
  border-bottom: 2px solid rgba($accent, 0.2);
  flex-shrink: 0;
  h3 {
    font-size: 1.25rem;
    font-weight: 700;
    color: $accent;
    margin: 0 0 10px 0;
  }
}
.review-modal-header .stars-row {
  display: flex;
  gap: 4px;
  justify-content: center;
}
.review-modal-header .stars-row :deep(svg) {
  width: 18px;
  height: 18px;
  color: $accent;
  fill: $accent;
}
.review-modal-body {
  padding: 20px 24px 24px;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
  flex: 1;
  min-height: 0;
}
.review-modal-text {
  font-size: 1rem;
  line-height: 1.7;
  color: #444;
  margin: 0 0 20px 0;
  white-space: pre-wrap;
}
.review-modal-scroll-hint {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  font-size: 0.8rem;
  color: #888;
  padding: 8px 0;
  flex-shrink: 0;
}
.review-modal-scroll-hint :deep(svg) {
  width: 16px;
  height: 16px;
}

.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.25s ease;
}
.modal-enter-active .review-modal,
.modal-leave-active .review-modal {
  transition: transform 0.25s ease;
}
.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}
.modal-enter-from .review-modal,
.modal-leave-to .review-modal {
  transform: scale(0.95);
}
</style>
