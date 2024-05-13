<template>
  <section class="contacts-timetable-section">
    <div>
      <div class="contacts-timetable-container">
        <h3 class="title">Orari</h3>
        <div class="timetables">
          <p><span>Martedí</span> – 15:00/19:00,</p>
          <p><span>Mercoledí</span> – 09:00/13:00-14:00/18:00</p>
          <p><span>Giovedí</span> – 09:00/13:00-14:00/18:00</p>
        </div>
      </div>
    </div>
    <div>
      <div class="contacts-timetable-container">
        <h3 class="title">Chiama</h3>
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
            <p><span class="details">Tel:</span><a href="tel:0000000">0000000</a></p>
            <p><span class="details">Whatsapp:</span><a href="https://wa.me/0000000">0000000</a></p>
            <p>
              <span class="details">Email:</span
              ><a href="mailto:marco@gmail.com">marco@gmail.com</a>
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
    border-bottom: 5px solid rgb(173, 216, 230);
    margin: 0 15px;
    margin: 25px 40px;
    .title {
      color: rgb(173, 216, 230);
      padding-bottom: 10px;
    }
    .timetables,
    .contact-details {
      p span {
        font-weight: bold;
      }
      p:last-child {
        padding-bottom: 25px;
      }
      .details {
        padding-right: 5px;
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
    border: 5px solid rgb(173, 216, 230);
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
