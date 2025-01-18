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
    <div id="contact-form" class="contact-section">
      <input type="text" placeholder="Nome" />
      <input type="email" placeholder="Email" />
      <textarea type="message" placeholder="Messaggio"></textarea>
      <div>
        <input type="checkbox" style="margin-right: 10px" />
        <span>Acconsento alla nostra informativa sulla <a href="">privacy</a></span>
      </div>
      <button>Invia</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactMain',

  components: {}
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
  }
}
</style>
