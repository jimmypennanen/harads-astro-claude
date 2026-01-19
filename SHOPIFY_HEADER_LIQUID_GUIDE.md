# Shopify Header Implementation Guide - Gläntan Edition

Om du föredrar att implementera headern själv i Shopify, eller om du vill veta exakt hur det bör se ut i kod, här är guiden:

## ALTERNATIV 1: Använd Shopify AI (Enklast)

Kopiera prompten från `SHOPIFY_HEADER_PROMPT.md` och ge den till Shopify AI.

---

## ALTERNATIV 2: Manuell Implementation i Shopify Theme Editor

### Steg 1: Hitta header-filen

1. Gå till **Online Store → Themes → Customize**
2. Klicka på **Edit code** (längst ner)
3. Sök efter och öppna: **sections/header.liquid**

### Steg 2: Ändra header-templatens CSS

I samma fil eller i **assets/custom.css**, lägg till detta CSS:

```css
/* ============================================
   GLÄNTAN HEADER CUSTOMIZATION
   ============================================ */

header {
  background-color: #f8f6f6 !important;
  border-bottom: 1px solid #ede8e8 !important;
}

/* Logo/Wordmark */
.header__heading,
.header__logo,
[data-header-logo] {
  color: #847949 !important;
  font-family: 'Cormorant Garamond', serif !important;
  font-weight: 700 !important;
  letter-spacing: 0.05em !important;
  font-size: 32px !important;
}

.header__logo img {
  height: 40px !important;
}

/* Menu links */
.header__menu-item a,
.header__link {
  color: #574444 !important;
  font-size: 16px !important;
}

.header__menu-item a:hover,
.header__link:hover {
  color: #847949 !important;
  text-decoration: underline !important;
}

/* Icons */
.header__icon,
[data-header-icon],
.cart-icon,
.search-icon,
.account-icon {
  color: #847949 !important;
}

.header__icon:hover,
[data-header-icon]:hover {
  color: #cbbdbd !important;
}

/* Sticky/Scroll behavior */
header.scrolled {
  height: 60px !important;
}

header.scrolled .header__logo {
  height: 30px !important;
}

/* Mobile menu */
.header__menu-button {
  background-color: transparent !important;
  border: none !important;
  color: #847949 !important;
}

.header__menu-button:hover {
  color: #cbbdbd !important;
}

/* Touch targets */
@media (max-width: 768px) {
  .header__icon,
  .header__menu-button,
  .header__link {
    min-width: 44px !important;
    min-height: 44px !important;
    display: flex !important;
    align-items: center !important;
    justify-content: center !important;
  }
}
```

### Steg 3: Justera header-inställningar i Shopify

1. **Gå till:** Theme customizer → Header
2. **Ändra:** Logo, Meny-items, ikoner
3. **Färgkontroll:** Kontrollera att bakgrunden är #f8f6f6

### Steg 4: Lägg till Cormorant Garamond-font

I **theme.liquid**, sök efter `<head>` och lägg till före andra fonts:

```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300..700;1,300..700&display=swap" rel="stylesheet">
```

---

## ALTERNATIV 3: Skapa Custom Header-Section

Om du vill total kontroll, skapa en ny section:

### 1. Skapa fil: `sections/header-glanten.liquid`

```liquid
<style>
  .glanten-header {
    background-color: #f8f6f6;
    padding: 16px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #ede8e8;
  }

  .glanten-header__logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 32px;
    font-weight: 700;
    color: #847949;
    text-decoration: none;
    letter-spacing: 0.05em;
  }

  .glanten-header__nav {
    display: flex;
    gap: 24px;
    align-items: center;
  }

  .glanten-header__nav a {
    color: #574444;
    text-decoration: none;
    font-size: 16px;
    transition: color 0.3s ease;
  }

  .glanten-header__nav a:hover {
    color: #847949;
    text-decoration: underline;
  }

  .glanten-header__icons {
    display: flex;
    gap: 16px;
    align-items: center;
  }

  .glanten-header__icon {
    background: none;
    border: none;
    color: #847949;
    cursor: pointer;
    font-size: 20px;
    transition: color 0.3s ease;
  }

  .glanten-header__icon:hover {
    color: #cbbdbd;
  }

  @media (max-width: 768px) {
    .glanten-header__nav {
      display: none;
    }

    .glanten-header__nav.active {
      display: flex;
      flex-direction: column;
      position: absolute;
      top: 60px;
      left: 0;
      right: 0;
      background: #f8f6f6;
      padding: 16px;
      gap: 12px;
    }
  }
</style>

<header class="glanten-header">
  <a href="/" class="glanten-header__logo">
    Gläntan
  </a>

  <nav class="glanten-header__nav">
    <a href="/">Hem</a>
    <a href="/collections">Sortiment</a>
    <a href="/pages/om-oss">Om oss</a>
    <a href="/pages/kontakt">Kontakt</a>
  </nav>

  <div class="glanten-header__icons">
    <button class="glanten-header__icon" aria-label="Sök">
      🔍
    </button>
    <a href="/cart" class="glanten-header__icon" aria-label="Varukorg">
      🛒
    </a>
    <button class="glanten-header__icon" aria-label="Meny">
      ☰
    </button>
  </div>
</header>

<script>
  document.querySelector('.glanten-header__icon:last-child').addEventListener('click', function() {
    document.querySelector('.glanten-header__nav').classList.toggle('active');
  });
</script>
```

---

## FÄRGREFERENS - KÖP OCH KLISTRA IN

```css
/* Kopiera dessa färgvariabler */
:root {
  --color-olive: #847949;
  --color-champagne: #f8f6f6;
  --color-beige: #ede8e8;
  --color-brown-beige: #cbbdbd;
  --color-brown: #574444;
}

/* Använd sedan i CSS */
header {
  background-color: var(--color-champagne);
}
```

---

## TESTA HEADERN

**Desktop (1920px):**
- ✅ Logo synlig och olivgrön
- ✅ Meny-länkar horisontella
- ✅ Ikoner (sök, varukorg, konto) synliga
- ✅ Bakgrund är #f8f6f6

**Tablet (768px):**
- ✅ Layout komprimerad
- ✅ Meny kan kollapsa

**Mobil (375px):**
- ✅ Hamburger-meny dyker upp
- ✅ Ikoner är minst 44x44px
- ✅ Responsiv layout

---

## NÄSTA STEG

1. **Implementera header** (välj Alternativ 1, 2, eller 3)
2. **Spara och preview** i Shopify
3. **Jämför med Astro-sidan** - se att designen matchar
4. **Testa på mobil** - se att det är lättanvänt
5. **Lås den** så den inte förändras av temuppdateringar

---

## BEHÖVER DU HJÄLP?

- Om du använder **Alternativ 1 (Shopify AI):** Kopiera prompten från `SHOPIFY_HEADER_PROMPT.md` och klistra in i Shopify AI
- Om du använder **Alternativ 2:** Följ stegen ovan steg-för-steg
- Om du använder **Alternativ 3:** Kopiera koden ovan och anpassa efter behov

Berätta vilket alternativ du väljer, så kan jag hjälpa dig vidare!
