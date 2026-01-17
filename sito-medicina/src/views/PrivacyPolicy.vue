<template>
  <section id="contact-main-section">
    <Menu />
    <div class="container">
      <h3>Privacy Policy</h3>

      <p>
        La protezione dei tuoi dati personali è per noi di fondamentale importanza. La presente
        Privacy Policy descrive come raccogliamo, utilizziamo e proteggiamo le tue informazioni
        quando utilizzi il nostro modulo di contatto per prenotazioni o richieste relative a
        informazioni ginecologiche.
      </p>

      <h4>1. Tipologia di Dati Raccolti</h4>
      <p>Raccogliamo i seguenti dati personali tramite il modulo di contatto:</p>
      <ul>
        <li><strong>Nome</strong>: per identificarti.</li>
        <li><strong>Email</strong>: per risponderti in merito alla tua richiesta.</li>
        <li>
          <strong>Messaggio</strong>: per comprendere il motivo della tua richiesta, che può
          riguardare una prenotazione o informazioni ginecologiche.
        </li>
      </ul>

      <h4>2. Finalità del Trattamento dei Dati</h4>
      <p>I tuoi dati saranno utilizzati esclusivamente per le seguenti finalità:</p>
      <ul>
        <li>Rispondere alle tue richieste relative a prenotazioni o informazioni ginecologiche.</li>
        <li>Fornirti supporto e assistenza in relazione a questioni ginecologiche.</li>
      </ul>

      <h4>3. Limitazione all'Utilizzo dei Dati</h4>
      <p>
        Ti informiamo che i tuoi dati non saranno utilizzati per scopi di marketing o per inviarti
        comunicazioni che non siano direttamente correlate alla tua richiesta di prenotazione o di
        informazioni ginecologiche. Non riceverai comunicazioni riguardanti promozioni, offerte
        commerciali o informazioni non pertinenti al tema ginecologico.
      </p>

      <h4>4. Modalità di Trattamento dei Dati</h4>
      <p>
        I tuoi dati saranno trattati in modo sicuro e confidenziale, attraverso sistemi informatici
        protetti. I dati saranno conservati solo per il tempo necessario a rispondere alla tua
        richiesta e per adempiere agli obblighi legali, se applicabili.
      </p>

      <h4>5. Condivisione dei Dati</h4>
      <p>
        I tuoi dati non saranno ceduti a terzi, ad eccezione di casi in cui sia richiesto dalla
        legge o da autorità competenti.
      </p>

      <h4>6. Diritti dell'Interessato</h4>
      <p>In qualità di interessato, hai il diritto di:</p>
      <ul>
        <li>Accedere ai tuoi dati personali.</li>
        <li>Richiedere la rettifica o la cancellazione dei tuoi dati.</li>
        <li>Opponerti al trattamento dei tuoi dati o limitarlo in determinate circostanze.</li>
        <li>
          Revocare il consenso in qualsiasi momento (salvo che il trattamento non sia necessario per
          obblighi legali).
        </li>
      </ul>
      <p>
        Per esercitare i tuoi diritti, puoi contattarci tramite l'indirizzo email [inserire
        indirizzo email].
      </p>

      <h4>7. Modifiche alla Privacy Policy</h4>
      <p>
        La presente Privacy Policy potrebbe subire modifiche. In tal caso, pubblicheremo le
        modifiche sulla presente pagina con la data dell'aggiornamento.
      </p>

      <h4>8. Consenso</h4>
      <p>
        Utilizzando il nostro modulo di contatto, dichiari di aver letto e compreso la presente
        Privacy Policy e acconsenti al trattamento dei tuoi dati personali come descritto.
      </p>
    </div>

    <div class="footer">
      <p>&copy; 2025 [Nome della tua Azienda]. Tutti i diritti riservati.</p>
    </div>
  </section>
</template>

<script>
import Menu from '../components/Menu/Menu.vue'
export default {
  name: 'PrivacyPolicy',

  data() {
    return {}
  },

  components: { Menu },

  methods: {}
}
</script>

<style scoped lang="scss">
* {
  margin: 0 0 20px 0;
}
h3 {
  color: #333;
  text-align: center;
}
h4 {
  color: #333;
}
p {
  font-size: 1rem;
  color: #555;
}
ul {
  margin-left: 20px;
}
.container {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  margin: 20px;
  max-width: 100%;
}
.footer {
  text-align: center;
  font-size: 0.8rem;
  margin-top: 40px;
}
</style>
