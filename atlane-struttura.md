# Atlante Vivo – Struttura & Convenzioni (Riferimento Tecnico)

Questo file tiene traccia della struttura del sito **Atlante Vivo**
ed è un punto di riferimento per mantenere ordine, coerenza e continuità.

Serve sia ad Alberto, sia ad Altheia (per ricostruire rapidamente il contesto
in future sessioni).

---

## 1. Struttura delle cartelle del progetto

```
atlante-vivo/
│
├── index.html                → Home dell’Atlante
├── capitolo-1.html           → Capitolo 1
├── capitolo-2.html           → Capitolo 2
├── capitolo-3.html           → Capitolo 3
├── capitolo-4.html           → Capitolo 4
│
├── images/                   → Immagini usate nei capitoli
│     ├── foto_vinili_fiera_del_disco.jpg
│     ├── canile-1.jpg
│     └── canile-2.jpg
│
├── audio/                    → Eventuali file audio futuri
├── video/                    → Eventuali file video futuri
│
└── atlante-struttura.md      → Questo file (documentazione interna)
```

---

## 2. Struttura generale di un capitolo

Ogni capitolo è una **pagina HTML indipendente**, con lo stesso stile e layout.

Schema:

```
<!DOCTYPE html>
<html>
  <head> … stile CSS identico per tutti i capitoli … </head>
  <body>
    <div class="wrapper">

      <header>… titolo Atlante …</header>

      <nav>
        <a href="index.html">← Torna alla Home</a>
      </nav>

      <main>
        <article class="post-card">

          <div class="post-meta">
            <span>Capitolo X</span> · [data] · [luogo]
          </div>

          <h2 class="post-title">Titolo del capitolo</h2>

          <div class="post-body">
            Testi, immagini, paragrafi, ecc.
          </div>

        </article>
      </main>

      <footer>© Alberto — Atlante Vivo</footer>

    </div>
  </body>
</html>
```

### Campi da aggiornare a ogni nuovo capitolo

* `<title>` nel `<head>`
* Numero del capitolo in `.post-meta`
* Data e luogo
* Titolo (`<h2 class="post-title">`)
* Contenuto in `.post-body`
* Eventuali immagini con percorso corretto

---

## 3. Regole per l’inserimento delle immagini

Tutte le immagini devono essere salvate nella cartella:

```
/images
```

e richiamate così:

```html
<img src="images/nomefile.jpg" alt="descrizione">
```

### Importante:

* GitHub Pages è **case-sensitive** → `images/` ≠ `Images/`.
* Nessun file multimediale nella root (ordine + percorsi stabili).

---

## 4. Struttura dell’`index.html`

L’index è la **home dell’Atlante**, e contiene:

* Titolo principale (“Atlante Vivo”)
* Sottotitolo
* Lista dei capitoli con link
* Ogni nuovo capitolo va aggiunto manualmente

Esempio di voce:

```html
<li><a href="capitolo-4.html">Capitolo 4 – Oggi al rifugio degli animali di Silvana</a></li>
```

### Ogni volta che si crea un capitolo:

1. Creare `capitolo-X.html`
2. Aggiungere il link corrispondente in `index.html`

---

## 5. Template di lavoro per creare rapidamente un nuovo capitolo

**Step-by-step:**

1. Duplica l’ultimo capitolo (es. `capitolo-4.html` → `capitolo-5.html`)
2. Cambia:

   * `<title>`
   * numero capitolo in `.post-meta`
   * data / luogo
   * titolo del capitolo `<h2>`
   * contenuto
3. Aggiungi immagini nella cartella `images/`
4. Aggiorna `index.html` con un nuovo `<li>`
5. Commit + push

---

## 6. Cartelle `audio/` e `video/` (per estensioni future)

Non sono ancora in uso attivo ma già predisposte.

### Esempio inserimento audio:

```html
<audio controls>
  <source src="audio/nometraccia.mp3" type="audio/mpeg">
</audio>
```

### Esempio inserimento video:

```html
<video controls>
  <source src="video/clip.mp4" type="video/mp4">
</video>
```

---

## 7. Debug: cosa fare se un capitolo “non si vede” o appare troncato

Checklist:

1. Verificare che il file HTML arrivi fino a `</html>`
2. Controllare che non ci siano caratteri invisibili dopo un `<p>` o `<h3>`
3. Confermare che le immagini puntino alla cartella giusta (`images/`)
4. Controllare la cache:

   * macOS: **⌘ + Shift + R**
   * oppure aprire in finestra anonima
5. Se GitHub Pages mostra una versione vecchia, attendere 30–60 secondi e ricaricare

---

## 8. Scopo di questo file

Questo documento:

* non viene usato dal sito
* serve come **memoria tecnica** dell’intero progetto
* aiuta a:

  * mantenere una struttura ordinata
  * ricostruire rapidamente come funziona un capitolo
  * evitare errori nei percorsi delle immagini
  * guidare l’aggiunta di nuovi contenuti

È il *filo di Arianna* del progetto Atlante Vivo.

---
