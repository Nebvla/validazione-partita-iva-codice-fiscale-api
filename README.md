# Validatore Partita IVA e Codice Fiscale (API REST)

Molti sviluppatori credono che per validare una Partita IVA o un Codice Fiscale italiano basti una semplice Espressione Regolare (Regex). **È un errore che porta a falsi positivi.**

Un utente potrebbe inserire `12345678901` in un form di checkout e passare il controllo Regex, ma quella Partita IVA è formalmente finta.

Per una validazione corretta è necessario applicare:
- **L'Algoritmo di Luhn** per calcolare l'11° carattere di controllo della Partita IVA.
- **L'algoritmo dei caratteri pari/dispari** (modulo 26) per calcolare il 16° carattere del Codice Fiscale.

## La Soluzione Rapida (Senza scrivere l'algoritmo)
Dover implementare, testare e mantenere questa logica matematica in PHP, JavaScript o Python per ogni progetto e-commerce è noioso.

Per questo ho creato un'**API REST gratuita e velocissima** che fa il calcolo per te in millisecondi.

👉 **[Usa l'API gratuitamente su RapidAPI]([https://rapidapi.com/Nebvla/api/italian-fiscal-code-vat-validator])**

### Come si usa (Esempio in JavaScript/Fetch)
```javascript
const url = 'https://[TUO_NOME_API][.p.rapidapi.com/valida/piva/00808160272](https://.p.rapidapi.com/valida/piva/00808160272)';
const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': 'LA_TUA_CHIAVE_RAPIDAPI',
		'X-RapidAPI-Host': '[TUO_NOME_API].p.rapidapi.com'
	}
};

try {
	const response = await fetch(url, options);
	const result = await response.text();
	console.log(result); // Restituisce {"valore": "00808160272", "tipo": "Partita IVA", "valida": true}
} catch (error) {
	console.error(error);
}
