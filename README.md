# Teknisk dokumentation – Dankort Øremærket - Team 1

## Om casen

Vi har fået til opgave at udvikle en digital løsning med udgangspunkt i Dankort Øremærket. Løsningen skal henvende sig til unge mellem 18 og 28 år og have til formål at skabe større interesse for, samt øge efterspørgslen på Dankort blandt den yngre målgruppe.

## Links

- GitHub repository:
- Netlify:
- Figma:

## Projektstruktur

Projektet er opdelt i HTML, CSS og JavaScript-filer.

```
├── public/
│   └── favicon_48x55.svg
├── assets
│    └──img
│    └──SVG
│
├── public/
│   └── favicon_48x55.svg
├── pages/
├── index.astro
├── counting.astro
├── filtering.astro
├── physicalcard.astro
│
├── css/
│   └──
│   └──
│
├── components/
│   ├── Advantages.astro
│   ├── Button.astro
│   ├── Buttonfiltering.astro
│   ├── Card.astro
│   ├── CardIndex.astro
│   ├── Faq.astro
│   ├── Footer.astro
│   ├── Guide.astro
│   ├── Header.astro
│   ├── Hero.astro
│   ├── Index_count.astro
│   ├── Partners.astro
│   ├── Physicalcard_comp.astro
│   ├── Physicalcard_index.astro
│   ├── Sec1filtering.astro
│   ├── Sec2counting.astro
│   ├── Sec3counting.astro
│   ├── Sec3filtering.astro
│   ├── Sec4counting.astro
│   └── Slideshow.astro
└── README.md
```

### Filbeskrivelser

- **index.astro** – forsiden
- **counting.astro** – viser tælleren for donationen
- **filtering.astro** – viser naturområder som Dankort Øremærket har doneret til.
- **physicalcard.astro** – viser fysisk dankort og hvordan man installere sit kort på mobil

- **'@fontsource-variable/raleway/wght.css'** – giver global font på alle siderne
- **<style is:global>** – global styling i Layout
- **JavaScript-filer** – styrer det dynamiske indhold, burgermenu og carousel

---

## Hvordan koden fungerer

Vi har tilføjet javascripten i de componenter det skulle bruges til på de forskellige sider.

### Header.astro

Bruges på alle sider. Indeholder burgermenu med Javascripten.

### Guide.astro

Har guide til hvordan man gør med gennem en carousel i Javascript.

### filtering.astro

Javascripten på denne side henter data fra Rest API'et via fetch og viser en liste over naturområder. Listen kan filtreres efter landsdel og nulstilles til at vise alle områder igen ved at trykke på knappen “Ryd filter”.

**Flow:**

1. Siden loader
2. JavaScript kører
3. Data hentes fra Rest API
4. Data bliver gennemgået med loop
5. HTML bliver indsat i DOM'en
6. Brugeren kan klikke på et naturområde og linke videre til naturfondens side

---

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                                    | Action                                             |
| :----------------------------------------- | :------------------------------------------------- |
| `npm install`                              | Installs dependencies                              |
| `npm run dev`                              | Starter den lokale dev server ved `localhost:4321` |
| `npm run build`                            | Bygger projektets side til `./dist/`               |
| `npm run preview`                          | Viser dit build lokalt, før du deployer            |
| `npm install @fontsource-variable/raleway` | Installerer den globale font Raleway i projektet.  |

## Navngivning

Vi har navngivet vores components, variabler og funktioner så de tydeligt som muligt er selvforklarende.

### Eksempler på variabler

```javascript
const endpoint;
const carousel;
const { Dankort } = Astro.props;
```

### Eksempler på funktioner

```javascript
function filtrer(e);
function burgerClick();
entries.forEach(entry =>);
```

Vi har brugt camelCase i vores JavaScript, fordi det gør koden mere ensartet og lettere at læse.

---

## Kommentarer i koden

Vi har kommenteret de steder i koden, hvor det giver mening.
Fx ved funktioner, fetch-kald og steder hvor der sker DOM-manipulation.

**Eksempel:**

```javascript

```

Vi har prøvet ikke at skrive kommentarer til helt åbenlyse ting, men kun dér hvor det hjælper forståelsen. I vores cssfiler har vi brugt det til bedre at kunne overskue hvor forskellige elementers styling ligger, da vi genbruger flere elementer på siderne.

---

## Data og JSON-struktur

Vi henter data fra et API i JSON-format.

**Et objekt kan fx se sådan ud:**

```json

id: 1

created_at 2026-05-19T10:28:37.287773+00:00

image: https://uigtgwaojslfwhlxfbfn.supabase.co/storage/v1/object/sign/Dankort%20EK/owl.webp?token=eyJraWQiOiJzdG9yYWdlLXVybC1zaWduaW5nLWtleV85MmNhYzIxZC1lZDViLTRmZmMtOGM1Ny0wNzc2MDIzOGJjOTgiLCJhbGciOiJIUzI1NiJ9.eyJ1cmwiOiJEYW5rb3J0IEVLL293bC53ZWJwIiwiaWF0IjoxNzc5MjU4Mzk1LCJleHAiOjE4MTA3OTQzOTV9.c47CHVannolEz-cFFZwHz0dBGW0R8N9HIAaIE3bHtF8;

link: https://naturfonden.dk/natur/skovene-paa-trelde-naes/

place: Trelde Næs

region: Jylland

svg: https://uigtgwaojslfwhlxfbfn.supabase.co/storage/v1/object/public/Dankort%20EK/owl.svg

```

### Felter vi bruger

- **id** – id på API
- **image** – URL til image
- **link** - til at linke til de forskellige sider på naturfondens hjemmeside
- **id** – gør at den vælger en bestemt limit med id og man kan vælge i array hvilke id man skal bruge.
- **region** – bruger vi til filtrering af stederne, som virker på knapperne over vores cards.
- **place** – viser stedets navn i card.
- **title** – jobtitel på companion
- **svg** – er forskellige svg´er der kommer frem gennem Supabase, når man laver hover på de forskellige cards.

---

## Validering

**HTML-validering:**

-
-
- ***

## Git og branches

Vi har brugt GitHub til at samarbejde om projektet.

Vi har arbejdet med branches, så vi ikke sad og ændrede i det samme på samme tid.

Vi navngav branches alt efter hvilke elementer/funktioner der blev lavet.

### Eksempler på branches

- `css-global`
- `tobias_components`
- `Hero-unit`
- `task_fysisk_kort_AB`

### Workflow

1. Lave en branch
2. Kode en feature
3. Committe ændringer
4. Pushe til GitHub
5. Merge til main når det virkede
6. Deploy til Netlify når alt er klar

Det gjorde det nemmere at holde styr på, hvem der lavede hvad.

---

## Bæredygtighed

Vi har tænkt bæredygtighed ind i projektet ved at holde page weight under 250 kb samt en enkel informationasarkitektur.

**Tiltag:**

- Ingen videoer
- Ingen tunge frameworks
- Genbruge kode så meget som muligt
- Optimerede billeder i webp og brugt Astro Image

---

## Udfordringer undervejs

En af vores udfordringer var at få data fra Rest API’et vist korrekt på siderne.
Det var også lidt svært at få id med videre i URL’en til detaljesiden.

**Løsninger:**

- Console.logge data undervejs
- Teste fetch-kald separat
- Bruge URLSearchParams
- Dele opgaverne mere tydeligt i gruppen

---

## Mulige forbedringer

Hvis vi skulle arbejde videre med projektet, kunne vi forbedre det ved at tilføje:

- En dynamisk tæller, gennem Javascript
-
- ***

## Gruppemedlemmer

- Annebeth Faurby Hansen
- Caroline Amalie Schytte Hemmingsen
- Julie Petersen Bosch
- Tobias Frouvne Vincentz
