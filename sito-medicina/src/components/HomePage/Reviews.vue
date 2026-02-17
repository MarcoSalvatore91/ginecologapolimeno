<template>
  <section id="reviews" class="reviews-wrap">
    <Carousel :wrap-around="true">
      <Slide v-for="(review, index) in reviews" :key="`${review.name}-${index}`">
        <div class="carousel__item">
          <div class="review-header">
            <h3>{{ review.name }}</h3>
            <div class="stars-row">
              <b-icon-star-fill v-for="star in 5" :key="star" />
            </div>
          </div>
          <div class="review-text">
            {{ review.text }}
          </div>
        </div>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>
  </section>
</template>

<script>
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

export default {
  name: 'Reviews',
  components: {
    Carousel,
    Slide,
    Navigation
  },

  data() {
    return {
      reviews: [
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

  methods: {}
}
</script>

<style scoped lang="scss">
$accent: #d97cb1;

.reviews-wrap {
  position: relative;
  padding: 0 28px;
}

#reviews :deep(.carousel__prev) {
  left: 20px;
}
#reviews :deep(.carousel__next) {
  right: 20px;
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
    transition: background 0.25s ease, transform 0.25s ease, box-shadow 0.25s ease;
    box-shadow: 0 2px 12px rgba(217, 124, 177, 0.35);
  }
  .carousel__prev:hover,
  .carousel__next:hover {
    background: darken($accent, 10%);
    transform: scale(1.08);
    box-shadow: 0 4px 16px rgba(217, 124, 177, 0.4);
  }
}
</style>
