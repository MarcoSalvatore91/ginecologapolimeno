<template>
  <section id="visits">
    <h2 class="section-title">Principali Prestazioni Eseguite</h2>
    <div class="visits-grid">
      <div class="visit-card" v-for="visit in visitList" :key="visit.title">
        <div class="visit-icon">
          <component :is="visit.icon" />
        </div>
        <h3 class="visit-title">{{ visit.title }}</h3>
        <p class="visit-text">{{ visit.content }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import {
  BIconHeartPulseFill,
  BIconCalendarHeartFill,
  BIconDisplayFill,
  BIconPersonBadgeFill,
  BIconClipboard2DataFill
} from 'bootstrap-icons-vue'

export default {
  name: 'Visits',

  components: {
    BIconHeartPulseFill,
    BIconCalendarHeartFill,
    BIconDisplayFill,
    BIconPersonBadgeFill,
    BIconClipboard2DataFill
  },

  data() {
    const icons = {
      BIconHeartPulseFill,
      BIconCalendarHeartFill,
      BIconDisplayFill,
      BIconPersonBadgeFill,
      BIconClipboard2DataFill
    }
    return {
      visitList: [
        {
          title: 'Visita Ginecologica',
          content:
            'Un controllo completo della salute femminile ad ogni età per prevenire e individuare precocemente eventuali disturbi, con un approccio attento e personalizzato.',
          icon: icons.BIconHeartPulseFill
        },
        {
          title: 'Visita Ostetrica',
          content:
            'Un incontro dedicato alla futura mamma per valutare l\'andamento della gravidanza, controllare pressione, peso, sintomi e fornire consigli personalizzati per ogni trimestre.',
          icon: icons.BIconCalendarHeartFill
        },
        {
          title: 'Visita Ostetrica e Ecografia Pelvica',
          content:
            'Esame ecografico immediato e rapido, eseguito per via sovrapubica e/o transvaginale, che permette di valutare con precisione utero e ovaie e identificare cisti, fibromi o altre alterazioni in modo accurato.',
          icon: icons.BIconDisplayFill
        },
        {
          title: 'Visita Ostetrica e Ecografia 3D',
          content:
            'Monitoraggio ecografico della gravidanza per seguire la crescita e il benessere del bambino, con ecografia anche in 3D, offrendo informazioni precise e tranquillità alla futura mamma.',
          icon: icons.BIconPersonBadgeFill
        },
        {
          title: 'Test Combinato / NIPT',
          content:
            'Screening del primo trimestre che integra ecografia e analisi del sangue per stimare il rischio di anomalie cromosomiche, aiutando a vivere la gravidanza con maggiore consapevolezza.',
          icon: icons.BIconClipboard2DataFill
        }
      ]
    }
  },

  methods: {}
}
</script>

<style scoped lang="scss">
$accent: #d97cb1;

#visits {
  padding: 32px 20px 72px;
  max-width: 1400px;
  margin: 0 auto;
}

.section-title {
  text-align: center;
  font-size: 1.75rem;
  font-weight: 700;
  color: #2c2c2c;
  margin-bottom: 40px;
  letter-spacing: -0.02em;
}

.visits-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}

.visit-card {
  background: white;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
  padding: 36px 28px;
  text-align: center;
  transition: box-shadow 0.25s ease, transform 0.25s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.visit-card:hover {
  box-shadow: 0 12px 36px rgba(0, 0, 0, 0.1);
  transform: translateY(-4px);
}

.visit-icon {
  width: 72px;
  height: 72px;
  margin: 0 auto 24px;
  border-radius: 16px;
  background: rgba($accent, 0.12);
  color: $accent;
  display: flex;
  align-items: center;
  justify-content: center;
}

.visit-icon :deep(svg) {
  width: 36px;
  height: 36px;
}

.visit-title {
  font-size: 1.1rem;
  font-weight: 700;
  color: #2c2c2c;
  margin-bottom: 14px;
  line-height: 1.3;
}

.visit-text {
  font-size: 0.9rem;
  color: #555;
  line-height: 1.65;
  margin: 0;
}

@media only screen and (min-width: 600px) {
  .visits-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media only screen and (min-width: 960px) {
  .visits-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 28px;
  }
}

@media only screen and (min-width: 1200px) {
  #visits {
    padding: 40px 32px 88px;
  }

  .section-title {
    font-size: 2rem;
    margin-bottom: 48px;
  }

  .visits-grid {
    grid-template-columns: repeat(5, 1fr);
  }

  .visit-card {
    padding: 40px 28px;
  }
}
</style>
