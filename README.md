# CLAUS — lloc públic

**CLAUS · Per entendre el món** és un panorama mensual geopolític i econòmic adreçat al ciutadà informat. És un lloc **estàtic** (HTML pur, sense servidor ni base de dades): cada número és una pàgina dissenyada que es versiona en aquest repositori.

> **Nota de marca.** CLAUS és un producte de vida pròpia. No ha de contenir **cap** enllaç, referència ni rastre cap a cap altre producte editorial. Res de peus, crèdits ni metadades que el connectin amb res més.

---

## Estructura del repositori

```
/
├── index.html            ← el número en curs (ara, el Número 0)
├── assets/
│   ├── claus-logo.png     ← logotip (transparent) per a reutilització
│   ├── favicon.png        ← icona de pestanya (el globus)
│   ├── hero-earth.jpg     ← imatge de portada  (cal afegir-la, vegeu més avall)
│   ├── afons-canal.jpg    ← imatge d'«A fons»  (cal afegir-la, vegeu més avall)
│   └── focus-banya.jpg    ← imatge del focus regional  (cal afegir-la, vegeu més avall)
└── README.md
```

Quan hi hagi més d'un número, l'estructura creixerà a `/numeros/2026-07.html`, `/numeros/2026-08.html`… i `index.html` passarà a ser una portada-arxiu. De moment, el Número 0 viu a l'arrel.

---

## Abans del primer desplegament: afegir les dues imatges

El logotip ja va **incrustat** dins de `index.html`, però les dues fotografies de contingut s'han de descarregar a `assets/`. Totes dues són de **domini públic (NASA)** i no requereixen atribució legal (tot i que la mantenim per bona pràctica). Des d'una terminal amb accés a internet, a l'arrel del repositori:

```bash
curl -L "https://commons.wikimedia.org/wiki/Special:FilePath/The_earth_at_night.jpg?width=2200" -o assets/hero-earth.jpg
curl -L "https://commons.wikimedia.org/wiki/Special:FilePath/New_Suez_Canal_aerial.jpeg?width=1500" -o assets/afons-canal.jpg
curl -L "https://commons.wikimedia.org/wiki/Special:FilePath/Ethiopia_hornafrica.jpg?width=1280" -o assets/focus-banya.jpg
```

- `hero-earth.jpg` — *Terra de nit* (NASA, domini públic)
- `afons-canal.jpg` — *Canal de Suez, vista aèria* (NASA, domini públic)
- `focus-banya.jpg` — *La Banya d'Àfrica, Blue Marble* (NASA, domini públic)

Comprova que `index.html` es veu bé obrint-lo al navegador **abans** de pujar-lo.

---

## Desplegament a Render (Static Site)

1. Crea un **repositori nou** a GitHub (pot ser privat; el lloc serà públic igualment) i puja-hi aquests fitxers, amb les dues imatges ja col·locades.
2. A Render: **New → Static Site → Connect** el repositori.
3. Configuració:
   - **Build Command:** *(deixa-ho buit)*
   - **Publish Directory:** `.` (l'arrel)
4. **Create Static Site.** Render desplega en segons i assigna una URL `*.onrender.com`. Cada `git push` a la branca principal redesplega automàticament.
5. **Domini propi (opcional):** Settings → Custom Domains. Recomanable un domini que **no** evoqui cap altre producte.

El pla gratuït de Static Site és suficient (CDN inclòs, HTTPS automàtic).

---

## Publicar un número nou

1. Es genera el nou `index.html` (o `/numeros/AAAA-MM.html`) amb la plantilla de CLAUS.
2. Es col·loquen les imatges del número a `assets/`.
3. `git add . && git commit -m "Número N — mes AAAA" && git push`
4. Render redesplega sol. Es verifica al navegador.

---

## Imatges i drets

Només s'hi fan servir imatges **lliures de drets** (domini públic, o llicències obertes com Wikimedia Commons / Unsplash / Pexels) amb la font registrada. Mai fotografia de premsa ni amb copyright.
