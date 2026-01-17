<template>
  <section class="contacts-timetable-section">
    <div>
      <div class="contacts-timetable-container">
        <h3 class="title">Ricevo presso</h3>
        <div class="timetables">
          <p>Ospedale Cristo Re, Via delle Calasanziane 25, 00167 Roma</p>
          <p>Mizar Medicina Specialistica, via Fosso dell’Osa , 603/605,  000132 Roma</p>
        </div>
      </div>
      <div class="contacts-timetable-container">
        <h3 class="title">Contatti Personali</h3>
        <div class="contact-details">
          <div>
            <p><span class="details">Telefono</span><a href="tel:3514959696">3514959696</a></p>
            <p>
              <span class="details">E-mail</span
              ><a id="e-mail" href="mailto:teresapolimeno.ginecologia@outlook.it"
                >teresapolimeno.ginecologia@outlook.it</a
              >
            </p>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="contacts-timetable-container">
        <h3 class="title">Contatti</h3>
        <div class="contact-details">
          <div>
            <p class="hidden">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Id fugit corporis ab eius
              illo placeat perspiciatis dignissimos explicabo?
            </p>
          </div>
          <div>
            <p><span>Per prenotazioni</span></p>
          </div>
          <div>
            <p>
              <span class="font-normal">Intramoenia presso Ospedale Cristo Re</span>
            </p>
            <p>
              <span class="details">Sito</span
              ><a href="https://ospedalecristore.it" target="_blank" rel="noopener noreferrer"
                >https://ospedalecristore.it</a
              >
            </p>
            <p><span class="details">Telefono</span><a href="tel:+3906612451">+3906612451</a></p>
            <!-- <p>
              <span class="details">Email:</span
              ><a id="e-mail" href="mailto:teresapolimeno.ginecologia@outlook.it"
                >teresapolimeno.ginecologia@outlook.it</a
              >
            </p> -->
            <p>
              <span class="font-normal">Mizar Medicina Specialistica</span>
            </p>
            <p>
              <span class="details">Telefono</span><a href="tel:+390659879859">+39 0659879859</a>
            </p>
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
.contacts-timetable-section {
  .contacts-timetable-container {
    border-bottom: 5px solid #fdc8eb66;
    margin: 0 15px;
    margin: 25px 40px;
    .title {
      color: #d97cb1;
      padding-bottom: 10px;
    }
    .timetables,
    .contact-details {
      p span {
        font-weight: bold;
      }
      p:last-child {
        padding-bottom: 25px;
        #e-mail {
          word-wrap: break-word;
        }
      }
      .details {
        padding-right: 5px;
      }
      .font-normal {
        font-weight: normal;
      }
      a:hover {
        background-color: transparent;
        color: #d97cb1;
      }
    }
  }
}

/* Responsive Desktop */

@media only screen and (min-width: 769px) {
  .hidden {
    display: none;
  }
  section.contacts-timetable-section {
    display: flex;
    border: 5px solid #fdc8eb66;
    margin: 30px 190px;
    div {
      width: 100%;
      border-bottom: none;
      .contacts-timetable-container {
        border-bottom: 0;
        .contact-details {
          p:last-child {
            padding-bottom: 0;
          }
        }
      }
    }
  }
}
</style>
