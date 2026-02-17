<template>
  <section id="contact-main-section">
    <div class="contact-main-wrap">
      <div class="contact-info">
        <p class="contact-intro">
          Per ricevere maggiori informazioni sui prodotti e servizi, non esitare a scrivermi via mail
          o compila il form di contatto. Sarete ricontattati al più presto.
        </p>
        <p class="contact-oppure">oppure</p>
        <p class="contact-subtitle">Prenota tramite uno dei seguenti contatti:</p>
        <div class="contact-details">
          <p><span class="details">Tel:</span> <a href="tel:3514959696">351 495 9696</a></p>
          <p>
            <span class="details">Whatsapp:</span>
            <a href="https://wa.me/393514959696" target="_blank" rel="noopener noreferrer"
              >351 495 9696</a
            >
          </p>
          <p>
            <span class="details">Email:</span>
            <a href="mailto:teresapolimeno.ginecologia@outlook.it"
              >teresapolimeno.ginecologia@outlook.it</a
            >
          </p>
        </div>
      </div>

      <div class="contact-form-wrap">
        <form id="contact-form" @submit.prevent="sendEmail">
          <input
            type="text"
            v-model="formData.name"
            placeholder="Nome"
            id="name"
            required
            autocomplete="name"
          />
          <input
            type="email"
            v-model="formData.email"
            placeholder="Email"
            id="email"
            required
            autocomplete="email"
          />
          <textarea
            v-model="formData.message"
            placeholder="Messaggio"
            id="message"
            rows="4"
          ></textarea>
          <div class="privacy-row">
            <input type="checkbox" id="privacy-check" required />
            <label for="privacy-check">
              Acconsento alla nostra informativa sulla
              <router-link to="/privacy-policy">privacy</router-link>
            </label>
          </div>
          <p v-if="statusMessage" class="form-status" :class="statusType">
            {{ statusMessage }}
          </p>
          <button type="submit" class="btn-invia" :disabled="sending">
            {{ sending ? 'Invio in corso...' : 'Invia' }}
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from '@emailjs/browser'

const EMAILJS_SERVICE = 'service_gbgnn3r'
const EMAILJS_TEMPLATE = 'template_2d0vnsz'
const EMAILJS_PUBLIC_KEY = 'kte2FiiFN9M-l4fsh'
// Template per notifica errori: crea su EmailJS un template con variabili {{error_message}}, {{name}}, {{email}}, {{message}}
// e inserisci qui l'ID (es. 'template_xxxxx'). Lascia vuoto per disattivare l'email in caso di errore.
const EMAILJS_ERROR_TEMPLATE = ''

export default {
  name: 'ContactMain',

  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      },
      statusMessage: '',
      statusType: '',
      sending: false
    }
  },

  components: {},

  methods: {
    async sendErrorNotification(error, templateParams) {
      if (!EMAILJS_ERROR_TEMPLATE) return
      try {
        await emailjs.send(
          EMAILJS_SERVICE,
          EMAILJS_ERROR_TEMPLATE,
          {
            error_message: error?.message || String(error),
            name: templateParams.name,
            email: templateParams.email,
            message: templateParams.message
          },
          EMAILJS_PUBLIC_KEY
        )
      } catch (e) {
        console.error('Invio email di errore fallito:', e)
      }
    },

    async sendEmail() {
      this.statusMessage = ''
      this.statusType = ''
      this.sending = true

      const { name, email, message } = this.formData
      const templateParams = { name, email, message }

      try {
        await emailjs.send(
          EMAILJS_SERVICE,
          EMAILJS_TEMPLATE,
          templateParams,
          EMAILJS_PUBLIC_KEY
        )
        this.statusMessage = 'Messaggio inviato con successo. Sarai ricontattato al più presto.'
        this.statusType = 'success'
        this.formData = { name: '', email: '', message: '' }
      } catch (error) {
        this.statusMessage =
          "Impossibile inviare il messaggio. Controlla la connessione o riprova più tardi."
        this.statusType = 'error'
        console.error('EmailJS error:', error)
        await this.sendErrorNotification(error, templateParams)
      } finally {
        this.sending = false
      }
    }
  }
}
</script>

<style scoped lang="scss">
$accent: #d97cb1;

#contact-main-section {
  padding: 40px 20px 64px;
  background: #fff;
}

.contact-main-wrap {
  max-width: 1360px;
  margin: 0 auto;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.contact-info {
  p {
    margin: 0 0 12px;
    color: #2c2c2c;
    font-size: 1rem;
    line-height: 1.6;
  }
  .contact-intro {
    margin-bottom: 16px;
  }
  .contact-oppure {
    font-weight: 600;
    color: #555;
  }
  .contact-subtitle {
    margin-bottom: 12px;
    font-weight: 600;
  }
}

.contact-details {
  p {
    margin: 0 0 8px;
  }
  .details {
    font-weight: 600;
    margin-right: 6px;
    color: #2c2c2c;
  }
  a {
    color: #2c2c2c;
    text-decoration: none;
    word-break: break-all;
    transition: color 0.2s;
  }
  a:hover {
    color: $accent;
  }
}

.contact-form-wrap {
  background: #fafafa;
  border-radius: 16px;
  padding: 32px 24px;
  border: 1px solid rgba(0, 0, 0, 0.06);
}

#contact-form {
  display: flex;
  flex-direction: column;
  gap: 0;

  input[type='text'],
  input[type='email'],
  textarea {
    width: 100%;
    margin: 0 0 16px;
    padding: 14px 16px;
    border: 1px solid rgba($accent, 0.35);
    border-radius: 12px;
    font-size: 1rem;
    font-family: inherit;
    background: #fff;
    transition: border-color 0.2s, box-shadow 0.2s;
    box-sizing: border-box;
  }
  input:focus,
  textarea:focus {
    outline: none;
    border-color: $accent;
    box-shadow: 0 0 0 3px rgba($accent, 0.15);
  }
  textarea {
    resize: vertical;
    min-height: 100px;
  }

  .privacy-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
    font-size: 0.9rem;
    color: #555;
    label {
      cursor: pointer;
    }
    a {
      color: $accent;
      text-decoration: none;
      font-weight: 500;
    }
    a:hover {
      text-decoration: underline;
    }
  }

  .form-status {
    margin: 0 0 16px;
    padding: 12px 16px;
    border-radius: 12px;
    font-size: 0.9rem;
    &.success {
      background: rgba(76, 175, 80, 0.12);
      color: #2e7d32;
    }
    &.error {
      background: rgba(244, 67, 54, 0.1);
      color: #c62828;
    }
  }

  .btn-invia {
    padding: 14px 28px;
    background: $accent;
    color: white;
    border: none;
    border-radius: 12px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s, opacity 0.2s;
    align-self: flex-start;
  }
  .btn-invia:hover:not(:disabled) {
    background: darken($accent, 8%);
  }
  .btn-invia:disabled {
    opacity: 0.7;
    cursor: not-allowed;
  }
}

@media only screen and (min-width: 769px) {
  .contact-main-wrap {
    flex-direction: row;
    align-items: center;
    gap: 48px;
  }

  .contact-info {
    flex: 0 0 42%;
  }

  .contact-form-wrap {
    flex: 1;
    padding: 36px 32px;
  }
}
</style>
