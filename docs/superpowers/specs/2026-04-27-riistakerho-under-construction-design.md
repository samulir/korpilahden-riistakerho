# Korpilahden Riistakerho — Väliaikainen "rakenteilla"-sivu

**Päivämäärä:** 2026-04-27
**Laajuus:** Yksi staattinen HTML-sivu

---

## Tarkoitus

Väliaikainen sivu, joka näytetään kunnes varsinainen sivusto valmistuu. Sivu viestii kerhon brändin ja kertoo sivuston olevan rakenteilla, sekä tarjoaa yhteystiedot lisätietoja varten.

---

## Tiedostot

| Tiedosto | Kuvaus |
|---|---|
| `index.html` | Sivun ainoa HTML-tiedosto |
| `kasvitausta-2-wide-web.jpg` | Optimoitu taustakuva (1920px, JPEG 85%, ~765KB) |
| `Riistakerho-logo.png` | Kerhon logo (alkuperäinen) |

Lähdetiedosto `kasvitausta-2-wide.png` (20MB) jää projektihallinnan käyttöön. Verkkosivu käyttää optimoitua `.jpg`-versiota.

---

## Visuaalinen identiteetti

- **Fontti:** Averia Serif Libre (Google Fonts) — käytetään kauttaaltaan, painotukset weight 300 ja 400
- **Väripaletti:**
  - Teksti (pää): `#f5efe0` — lämmin kerma
  - Teksti (tagline): `#f0e8d4` — vaaleampi kerma
  - Teksti (yhteystiedot): `#ecdfc6`
  - Aksentti / koristeet: `#c8a85a` — kullanruskea
  - Sähköposti: `#c9b99a`
  - Tausta (fallback): `#0d1a0d` — syvä tummanvihreä
- **Taustakuva:** Leveä metsäjärvi-kuvitus, vintage-puupiirrostyyliä
- **Overlay:** Radiaaligradientti-vignetti — `radial-gradient(ellipse at center, rgba(8,20,8,0.10) 0%, rgba(6,16,6,0.80) 100%)`

---

## Rakenne ja layout

Sivu on täysikorkuinen (`min-height: 100vh`), sisältö pystysuunnassa ja vaakasuunnassa keskitetty.

```
[ Taustakuva + vignette-overlay ]
        ┌──────────────────┐
        │      LOGO        │  240×240px, drop-shadow
        │   ✦ ─────── ✦   │  kultainen erotinlinja
        │ Sivusto on       │
        │ rakenteilla      │  h1, #f5efe0
        │ Korpilahden...   │  italic tagline, #f0e8d4
        │   ✦ ─────── ✦   │
        │   LISÄTIETOJA    │  uppercase label, #c8a85a
        │  Samuli Raappana │
        │  ym.metsasta...  │  mailto-linkki
        └──────────────────┘
```

---

## Sisältö

| Elementti | Arvo |
|---|---|
| Pääotsikko | Sivusto on rakenteilla |
| Tagline | Korpilahden Riistakerho avaa sivustonsa pian. Palataan asiaan! |
| Yhteystietojen otsikko | Lisätietoja |
| Yhteyshenkilö | Samuli Raappana |
| Sähköposti | ym.metsastajat@gmail.com (klikattava mailto-linkki) |

---

## Tekniset vaatimukset

- **Ei riippuvuuksia** (ei frameworkeja, ei JS-kirjastoja) — puhdas HTML + CSS
- **Google Fonts** ladataan CDN:stä: Averia Serif Libre (300, 400, italic)
- **Responsiivisuus:** Toimii sekä desktop- että mobiiliruudulla; logo pienenee, teksti skaalautuu `clamp()`-funktiolla
- **Saavutettavuus:** Logo-kuvalla `alt`-teksti, sähköpostilinkki semanttisena `<a href="mailto:...">` -elementtinä
- **Meta:** `lang="fi"`, viewport-meta, charset UTF-8

---

## Rajaukset

- Ei analytiikkaa, ei evästeilmoitusta
- Ei sosiaalisen median linkkejä tässä vaiheessa
- Ei animaatioita (paitsi hover-siirtymä sähköpostilinkissä)
- Ei palvelinpuolen koodia — staattinen tiedosto
