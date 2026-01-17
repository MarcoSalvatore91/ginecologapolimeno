<template>
  <section id="contact-main-section">
    <div class="contact-section">
      <p>
        Per ricevere maggiori informazioni sui prodotti e servizi, non esitare a scrivermi via mail
        o compila il form di contatto. Sarete ricontattati al più presto.
      </p>
      <p>oppure</p>
      <p>Prenota tramite uno dei seguenti contatti:</p>
      <div class="contact-details">
        <p><span class="details">Tel:</span><a href="tel:3514959696">3514959696</a></p>
        <p>
          <span class="details">Whatsapp:</span><a href="https://wa.me/3514959696">3514959696</a>
        </p>
        <p>
          <span class="details">Email:</span
          ><a id="e-mail" href="mailto:teresapolimeno.ginecologia@outlook.it"
            >teresapolimeno.ginecologia@outlook.it</a
          >
        </p>
      </div>
    </div>
    <form id="contact-form" class="contact-section" @submit.prevent="sendEmail">
      <input type="text" v-model="formData.name" placeholder="Nome" id="name" required />
      <input type="email" v-model="formData.email" placeholder="Email" id="email" required />
      <textarea
        type="message"
        v-model="formData.message"
        placeholder="Messaggio"
        id="message"
      ></textarea>
      <div>
        <input type="checkbox" style="margin-right: 10px" required />
        <span
          >Acconsento alla nostra informativa sulla
          <router-link id="privacy-policy" to="/privacy-policy">privacy</router-link></span
        >
      </div>
      <button type="submit">Invia</button>
    </form>
  </section>
</template>

<script>
import emailjs from '@emailjs/browser'

export default {
  name: 'ContactMain',

  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      },
      statusMessage: ''
    }
  },

  components: {},

  methods: {
    async sendEmail() {
      const { name, email, message } = this.formData
      const templateParams = {
        name: name,
        email: email,
        message: message
      }

      try {
        const response = await emailjs.send(
          'service_gbgnn3r', // Sostituisci con il tuo Service ID
          'template_2d0vnsz', // Sostituisci con il tuo Template ID
          templateParams,
          'kte2FiiFN9M-l4fsh' // Sostituisci con la tua Public Key
        )
        this.statusMessage = 'Email inviata con successo!'
        console.log('SUCCESS:', response)
      } catch (error) {
        this.statusMessage = "Errore durante l'invio dell'email."
        console.error('FAILED:', error)
      }
    }
  }
}
</script>

<style scoped lang="scss">
#contact-main-section {
  display: flex;
  justify-content: center;
  .contact-section {
    width: 40%;
    margin-top: 30px;
  }
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
    a:hover {
      background-color: transparent;
      color: #d97cb1;
    }
  }
  #contact-form {
    display: flex;
    flex-direction: column;
    input {
      margin: 10px 0;
      padding: 10px;
      border: 1px solid #d97cb1;
    }
    textarea {
      margin: 10px 0;
      padding: 10px;
      height: 100px;
      border: 1px solid #d97cb1;
    }
    button {
      margin: 10px 0;
      padding: 10px;
      background-color: #d97cb1;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      width: 100px;
    }
    #privacy-policy {
      color: #d97cb1;
      text-decoration: none;
    }
    #privacy-policy:hover {
      background-color: transparent;
    }
  }
}
</style>
