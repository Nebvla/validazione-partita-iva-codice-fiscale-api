# Validatore Partita IVA e Codice Fiscale (API REST)

Molti sviluppatori utilizzano semplici Espressioni Regolari (Regex) per validare i dati fiscali italiani. **Questo è un errore** che permette l'inserimento di dati formalmente falsi (es. `12345678901` passa una regex ma non è una P.IVA esistente).

Per una validazione reale e professionale è necessario applicare il controllo algoritmico:
- **Algoritmo di Luhn** per il calcolo dell'undicesimo carattere della Partita IVA.
- **Controllo Omocodia e Carattere di Controllo (Modulo 26)** per il Codice Fiscale.

## 🚀 Soluzione Pronta all'Uso
Invece di riscrivere, testare e manutenere la logica matematica in ogni singolo progetto, puoi utilizzare questa API REST gratuita, sicura e velocissima.

👉 **[Accedi all'API su RapidAPI](https://rapidapi.com/Nebvla/api/italian-fiscal-code-vat-validator)**

### Esempio di integrazione (JavaScript Fetch)

```javascript
const url = '[https://italian-fiscal-code-vat-validator.p.rapidapi.com/valida/cf/RSSMRA80A01H501W](https://italian-fiscal-code-vat-validator.p.rapidapi.com/valida/cf/RSSMRA80A01H501W)';
const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': 'LA_TUA_CHIAVE_RAPIDAPI', // Recuperala dalla dashboard di RapidAPI
		'X-RapidAPI-Host': 'italian-fiscal-code-vat-validator.p.rapidapi.com'
	}
};

try {
	const response = await fetch(url, options);
	const result = await response.json();
	console.log(result); 
    // Output: {"valore": "RSSMRA80A01H501W", "tipo": "Codice Fiscale", "valida": true}
} catch (error) {
	console.error("Errore durante la validazione:", error);
}
```
## Perchè usare questa API?
- **Velocità**: Risposte ottimizzate in millisecondi (Server in Europa).
- Affidabilità: Implementazione rigorosa degli algoritmi ufficiali dell'Agenzia delle Entrate.
- Modello Freemium: Piano gratuito per test e piccoli volumi, scalabile per e-commerce ad alto traffico.
- Nessuna dipendenza: Funziona con qualsiasi linguaggio (Python, PHP, JS, Ruby, ecc.) senza installare librerie pesanti.

Ideale per checkout Shopify, WooCommerce, Magento e form di registrazione aziendali.
