# Korpilahden Riistakerho — Rakenteilla-sivu, toteutussuunnitelma

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Luoda yksi staattinen `index.html`-tiedosto, joka toimii Korpilahden Riistakerho -sivuston väliaikaisena "rakenteilla"-sivuna.

**Architecture:** Puhdas HTML + CSS ilman riippuvuuksia. Google Fonts ladataan CDN:stä. Kaikki tyyli sisäisessä `<style>`-lohkossa. Ei JavaScriptiä, ei build-vaihetta.

**Tech Stack:** HTML5, CSS3, Google Fonts (Averia Serif Libre)

---

## Tiedostorakenne

```
/Korpilahden Riistakerho/
├── index.html                    ← luodaan tässä suunnitelmassa
├── kasvitausta-2-wide-web.jpg    ← valmis (optimoitu 1920px JPEG 85%)
└── Riistakerho-logo.png          ← valmis (alkuperäinen)
```

---

### Task 1: Luo index.html — dokumenttirunko ja metatiedot

**Files:**
- Create: `index.html`

- [ ] **Step 1: Luo tiedosto ja perusrunko**

Luo `/Users/samuliraappana/Documents/GitHub/Korpilahden Riistakerho/index.html` seuraavalla sisällöllä:

```html
<!DOCTYPE html>
<html lang="fi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="robots" content="noindex">
  <title>Korpilahden Riistakerho</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Averia+Serif+Libre:ital,wght@0,300;0,400;0,700;1,300;1,400&display=swap" rel="stylesheet">
  <style>
    /* placeholder — lisätään Task 2:ssa */
  </style>
</head>
<body>
  <!-- placeholder — lisätään Task 3:ssa -->
</body>
</html>
```

- [ ] **Step 2: Avaa tiedosto selaimessa ja varmista että se aukeaa tyhjänä sivuna**

```bash
open "/Users/samuliraappana/Documents/GitHub/Korpilahden Riistakerho/index.html"
```

Odotettu tulos: Tyhjä sivu avautuu, selaimen otsikkorivi näyttää "Korpilahden Riistakerho".

---

### Task 2: Lisää CSS-tyylit

**Files:**
- Modify: `index.html` — `<style>`-lohko

- [ ] **Step 1: Korvaa `<style>`-lohkon sisältö kokonaisella tyylimäärittelyllä**

```css
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Averia Serif Libre', serif;
  background: #0d1a0d;
  min-height: 100vh;
}

.page {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  overflow: hidden;
}

.bg {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 40%;
  z-index: 0;
}

.vignette {
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at center, rgba(8,20,8,0.10) 0%, rgba(6,16,6,0.80) 100%);
  z-index: 1;
}

.content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  max-width: 560px;
  width: 100%;
}

.logo {
  width: 240px;
  height: 240px;
  object-fit: contain;
  filter: drop-shadow(0 8px 32px rgba(0,0,0,0.6));
  margin-bottom: 32px;
}

.divider {
  display: flex;
  align-items: center;
  gap: 14px;
  width: 100%;
  max-width: 300px;
  margin-bottom: 24px;
}

.divider-line {
  flex: 1;
  height: 1px;
  background: rgba(200,184,140,0.4);
}

.divider-star {
  color: #c8a85a;
  font-size: 0.9rem;
}

.heading {
  font-size: clamp(1.6rem, 4vw, 2.1rem);
  font-weight: 400;
  color: #f5efe0;
  letter-spacing: 0.05em;
  line-height: 1.35;
  margin-bottom: 14px;
  text-shadow: 0 2px 16px rgba(0,0,0,0.7);
}

.tagline {
  font-size: clamp(0.88rem, 2vw, 1rem);
  font-weight: 300;
  color: #f0e8d4;
  letter-spacing: 0.06em;
  line-height: 1.65;
  margin-bottom: 36px;
  font-style: italic;
  text-shadow: 0 2px 14px rgba(0,0,0,0.75);
}

.contact-block {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 7px;
  margin-top: 8px;
}

.contact-label {
  font-size: 0.68rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: #c8a85a;
  margin-bottom: 4px;
}

.contact-name {
  font-size: 0.98rem;
  font-weight: 400;
  color: #ecdfc6;
  letter-spacing: 0.04em;
  text-shadow: 0 1px 8px rgba(0,0,0,0.6);
}

.contact-email {
  font-size: 0.92rem;
  color: #c9b99a;
  text-decoration: none;
  letter-spacing: 0.04em;
  border-bottom: 1px solid rgba(200,184,140,0.35);
  padding-bottom: 2px;
  transition: color 0.2s, border-color 0.2s;
}

.contact-email:hover {
  color: #f0dda0;
  border-bottom-color: rgba(240,221,160,0.55);
}
```

- [ ] **Step 2: Tarkista selaimessa**

Päivitä sivu selaimessa. Tausta on nyt `#0d1a0d` (tumma vihreä). Muuta ei vielä näy.

---

### Task 3: Lisää HTML-sisältö

**Files:**
- Modify: `index.html` — `<body>`-lohko

- [ ] **Step 1: Korvaa `<body>`-elementti kokonaisella rakenteella**

```html
<body>
  <div class="page">
    <img
      class="bg"
      src="kasvitausta-2-wide-web.jpg"
      alt=""
      aria-hidden="true"
    >
    <div class="vignette"></div>

    <div class="content">
      <img
        class="logo"
        src="Riistakerho-logo.png"
        alt="Korpilahden Riistakerho"
      >

      <div class="divider" aria-hidden="true">
        <div class="divider-line"></div>
        <span class="divider-star">✦</span>
        <div class="divider-line"></div>
      </div>

      <h1 class="heading">Sivusto on rakenteilla</h1>
      <p class="tagline">
        Korpilahden Riistakerho avaa sivustonsa pian.<br>
        Palataan asiaan!
      </p>

      <div class="divider" aria-hidden="true">
        <div class="divider-line"></div>
        <span class="divider-star">✦</span>
        <div class="divider-line"></div>
      </div>

      <div class="contact-block">
        <p class="contact-label">Lisätietoja</p>
        <p class="contact-name">Samuli Raappana</p>
        <a
          class="contact-email"
          href="mailto:ym.metsastajat@gmail.com"
        >ym.metsastajat@gmail.com</a>
      </div>
    </div>
  </div>
</body>
```

- [ ] **Step 2: Tarkista selaimessa — visuaalinen tarkistuslista**

Päivitä sivu ja varmista kaikki kohdat:

- [ ] Taustakuva (metsäjärvi-kuvitus) näkyy koko ruudun leveydeltä
- [ ] Vignetti tummentaa reunoja — keskellä kuva on vaaleampi
- [ ] Logo näkyy 240px koossa, pyöreä, ilman valkoista taustaa
- [ ] Kultainen erotinlinja `✦` näkyy logon alapuolella
- [ ] Otsikko "Sivusto on rakenteilla" vaaleankermainen, selkeästi luettava
- [ ] Tagline kursiivilla, vaaleampi sävy, kaksirivinen
- [ ] Toinen erotinlinja taglinesin alapuolella
- [ ] "LISÄTIETOJA" pienin kultaisin kirjaimin
- [ ] "Samuli Raappana" ja sähköpostiosoite näkyvät
- [ ] Sähköpostilinkki avaa sähköpostiohjelman klikattaessa
- [ ] Hover-efekti sähköpostilinkissä toimii (väri vaalenee)

- [ ] **Step 3: Tarkista mobiilissa tai kapealla selainikkunalla (< 480px)**

Kavenna selainikkuna kapeaksi tai käytä DevToolsin mobiiliemulaattoria. Varmista:

- [ ] Logo skaalautuu ruudun leveyden mukaan eikä leikkaudu
- [ ] Teksti on luettavaa
- [ ] Sivusto pysyy yhteen ruutuun (ei vieritettävää sisältöä sivusuunnassa)

---

### Task 4: Fontti-fallback ja viimeistely

**Files:**
- Modify: `index.html` — `<style>`-lohko, `body`-sääntö

- [ ] **Step 1: Varmista fonttien lataus offline-tilassa**

Avaa selain DevTools → Network-välilehti → aseta "Offline"-tila päälle. Päivitä sivu.

Odotettu tulos: Sivun rakenne ja layout säilyvät, fontti putoaa selaimen serif-fallbackiin (esim. Georgia). Sivu on edelleen toimiva ja luettava.

Poista offline-tila.

- [ ] **Step 2: Lisää eksplisiittinen fontti-fallback `body`-sääntöön**

Muuta `body`:n `font-family`-arvo:

```css
font-family: 'Averia Serif Libre', Georgia, 'Times New Roman', serif;
```

- [ ] **Step 3: Tarkista valmis sivu kerran läpi**

Avaa sivu uudessa selainikkunassa (välimuisti tyhjänä: Cmd+Shift+R / Ctrl+Shift+R).

Lopullinen tarkistuslista:
- [ ] Kaikki Task 3 Step 2:n kohdat edelleen kunnossa
- [ ] Sivun title on "Korpilahden Riistakerho"
- [ ] `<meta name="robots" content="noindex">` estää hakukoneet (tarkista lähdekoodista)
- [ ] Fontti on Averia Serif Libre (DevTools → Elements → Computed → font-family)
