# 📚 Manuale d'Uso: Atypical Med

Benvenuta nel manuale del tuo sito!
Questo documento ti spiega come visualizzare il sito sul tuo computer, come scrivere nuovi articoli e come pubblicarli online.

---

## 🧭 Pagine del Sito

|Nome        |Url|Descrizione|
|------------|---|-----------|
|**Home**    |`/`   |La vetrina principale con la tua presentazione.
|**About**  |`/about/`   |La pagina dove racconti la tua storia.
|**Blog**    |`/blog/`   |L'indice di tutti i tuoi articoli.
|**Articoli**|`/categoria/AAAA/MM/GG/titolo-articolo.html`   |Le singole pagine dove racconti le tue esperienze.
|**Categorie**|`/blog/nome-categoria/`|Le pagine dedicate alle categorie di articoli.
|**404**     |   |Pagina d'errore.

---

## 🛠 Prerequisiti

Per lavorare al sito dal tuo computer, assicurati di avere aperti:
1.  **Docker Desktop** (Il motore che fa girare il sito in locale).
2.  **GitHub Desktop** (Il programma per salvare e pubblicare le modifiche).
3.  **Visual Studio Code** (Il programma che usi per scrivere i testi).

---

## 🚀 Installazione (Solo la prima volta)

*Esegui questi comandi solo la prima volta o se cambi computer o reinstalli tutto da zero.*

Apri la cartella del progetto su Visual Studio Code e nel terminale incolla ed esegui il seguente comando:
```bash
docker compose run --rm site bundle install
```

---

## ▶️ Avvio Giornaliero (Come vedere il sito e modifiche locali in diretta)

Ogni volta che vuoi lavorare al blog, segui questi 2 passi:

1.  **Avvia il server:**
    Hai due possibilità equivalenti:
    - Dal terminale di Visual Studio Code lancia questo comando:
    ```bash
    docker compose up
    ```
    - Oppure, avvia il container `atypicalmed` da Docker Desktop

2.  **Apri il browser:**
    * Vai su: [http://localhost:4000](http://localhost:4000)
    
    Da questo momento, ogni volta che salvi un file di testo, il sito si aggiornerà da solo in pochi secondi! ✨

---

## ✍🏾 Come scrivere un nuovo articolo

### 1. Crea il file
Vai nella cartella `_posts`. Crea un nuovo file seguendo rigorosamente questa regola per il nome (è fondamentale per l'ordine cronologico):
`AAAA-MM-GG-titolo-che-vuoi.md`

> Esempio: `2026-01-05-la-mia-prima-gita-in-erasmus.md`

### 2. Imposta i dati (L'intestazione)
Copia e incolla questo blocco in cima al tuo nuovo file:

```yaml
---
layout: post
title:  "Titolo del tuo Articolo"
date:   2026-01-05 12:00:00 +0100
categories: [Viaggi, Erasmus]
author: Tuo Nome
---

```

**Note importanti:**

* **Date:** Se metti una data futura, l'articolo **non** apparirà finché non arriva quel giorno.
* **Fuso orario:** `+0100` (Inverno), `+0200` (Estate).
* **Categories:** Le etichette che appariranno colorate. Scrivile tra parentesi quadre.

### 3. Scrivi il contenuto

Sotto i trattini `---`, scrivi liberamente la tua storia.
Puoi usare il grassetto, i link e le liste. Nella sezione successiva ci sarà una breve guida alla scrittura in Markdown.

## 📝 Breve guida su Markdown

### 1. Formattazione testo 🔤
* Usa gli hashtag `#` per scrivere titoli, sottotitoli, sotto-sottotitoli ecc. e ordinare così logicamente il contenuto del tuo articolo. Ad esempio:
    ```markdown
    # Titolo dell'articolo

    ## Sezione 1

    ### Sotto-sezione 1.1

    ### Sotto-sezione 1.2

    ## Sezione 2

    ### Sotto-sezione 2.1

    #### Sotto-sotto-sezione 2.1.1

    ### Sotto-sezione 2.2
    ```

* Per il **grassetto** usa due asterischi: `**Testo**`.
* Per il *corsivo* usa un asterisco: `*Testo*`.
* Per i link: `[Testo del link](https://google.com)`.

### 2. Elenchi 📋

* Per inserire un elenco puntato:
  ```markdown
  * Mela
  * Pera
  * Banana
  ```
* Per inserire un elenco numerato:
  ```markdown
  1. Primo item
  2. Secondo item
  3. Eccetera...
  ```

### 3. Inserire immagini 📸

1. Metti la tua foto (es. `foto-mare.jpg`) nella cartella `assets/images/` del progetto.
2. Nel punto dell'articolo dove vuoi che appaia, scrivi:
```markdown
![Descrizione della foto](/assets/images/foto-mare.jpg)
```

### 4. Inserire video 🎬

1. Metti il tuo video (es. `video-lubiana.MOV`) nella cartella `assets/videos/` del progetto.
2. Nel punto dell'articolo dove vuoi che appaia, scrivi:
```markdown
{% include video.html path="/assets/videos/mio-lubiana.MOV" %}
```

---

## 💾 Salvare e Pubblicare (GitHub Desktop)

Quando sei soddisfatta del risultato che vedi su *localhost*:

1. Apri **GitHub Desktop**.
2. Vedrai la lista dei file modificati sulla sinistra.
3. In basso a sinistra, scrivi un titolo per il salvataggio (es: "Scritto nuovo articolo su Barcellona").
4. Clicca sul bottone blu **Commit to main** (Questo salva sul tuo computer).
5. Clicca in alto a destra su **Push origin** (Questo pubblica online).

*Attendi qualche minuto e le modifiche saranno visibili sul sito vero!*

---

## Struttura delle cartelle del progetto

Di seguito una breve guida sulla funzione dei vari file e cartelle contenuti nel progetto:
```markdown
│
├── index.md               🏠 Home page del sito
├── about.md               🧑🏾‍🦱 Pagina dove racconti la tua storia.
├── 404.html               🤷🏿 Pagina di errore "non trovato"
│
├── _posts/                ✍🏾 Articoli del blog
│
├── assets/                📦 Risorse
│   ├── images/            📸 Foto del sito e blog. Inserisci qui le immagini.
│   └── main.scss          ⚠️ File di collegamento stile, non toccare
│
├── blog/                  📰 Pagine del blog "non-articoli".
│   ├── index.md           Pagina principale del blog che elenca tutti i tuoi post
│   └── erasmus.md         Pagina del blog specifica per la categoria Erasmus
│
├── _sass/                 🎨 GRAFICA. Qui si modificano colori, font, ...
│   ├── _base.scss         Stili generali come i bottoni
│   ├── _blog.scss         Stile degli articoli e del blog
│   ├── _landing.scss      Stile della home page
│   └── _variables.scss    Tavolozza dei colori e i font
│
│
⚠️ Area Tecnica: NON TOCCARE!
│
├── _layouts/              ⚠️ GRAFICA personalizzata (non toccare)
│   ├── _landing.html      Grafica personalizzata landing page
│
├── _config.yml            ⚙️ IMPOSTAZIONI GENERALI. Titolo del sito, autore, ecc.
│                          Se modifichi questo, devi riavviare Docker
├── .gitignore
├── .vscode/
├── Gemfile
├── docker-compose.yml     Il motore che fa girare il sito
├── README.md              Questo manuale
```