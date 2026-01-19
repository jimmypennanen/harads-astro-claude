# Shopify AI Footer Prompt - Gläntan Gårdsbutik

Kopiera och klistra in denna prompt direkt i Shopify AI eller din AI-assistent:

---

## PROMPT:

Du ska designa en footer för en Shopify Dawn-tema butik som heter "Gläntan" (en gårdsbutik för djurfoder i Harads, Sverige). Footern ska matcha och spegla designen på Astro-webbplatsen för Gläntan.

### DESIGN KRAV - LAYOUT & STRUKTUR:

**Bakgrund & Färger:**
- Bakgrundsfärg: #f8f6f6 (champagne - mycket ljust beige)
- Text färg primär: #847949 (olivgrön)
- Text färg secondary: #574444 (brun)
- Hover färg: #cbbdbd (brunbeige)
- Border färg: #847949 (olivgrön)
- Shadow: Subtil skugga längst upp (inset shadow)

**Grid Layout (Desktop 4 kolumner):**

```
┌─────────────────────────────────────────────────┐
│                   FOOTER                        │
├─────────────┬─────────────┬─────────────┬────────┤
│   NAVEGATION│  SHOP LINKS │  CUSTOMER   │CONTACT │
│             │             │    CARE    │        │
│  - Hem      │ - Hundfoder │ - FAQ      │INFO:   │
│  - Butik    │ - Kattfoder │ - Shipping │        │
│  - Om oss   │ - Hästfoder │ - Returns  │Gläntan │
│  - Kontakt  │ - Hönsford. │ - Contact  │123     │
│             │ - Kanin &M. │            │        │
│             │ - Vilt      │            │960 24  │
│             │ - Vildfåglar│            │Harads  │
│             │ - Planterin │            │        │
│             │             │            │info@   │
│             │             │            │glantan │
│             │             │            │.com    │
│             │             │            │        │
│             │             │            │070-123 │
│             │             │            │45 67   │
├─────────────┴─────────────┴─────────────┴────────┤
│                   COPYRIGHT BAR                  │
│  © 2025 Gläntan | Alla rättigheter förbehållna │
└────────────────────────────────────────────────┘
```

### KOLUMN 1: NAVIGATION

**Rubrik:** Ingen (eller "Navigation" diskret)

**Länkgrupp:**
- Hem
- Butik (eller "Shop")
- Om oss (eller "Om Gläntan")
- Kontakt

**Styling:**
- Länk-färg: #847949 (olivgrön)
- Text-transform: UPPERCASE
- Font-size: 14px
- Letter-spacing: 0.05em
- Hover: #cbbdbd (brunbeige) + underline
- Spacing mellan links: 8px vertikalt
- Line-height: 1.6

### KOLUMN 2: SHOP/KATEGORIER

**Rubrik:** "Handla" eller "Shop"
- Font: Bold
- Färg: #847949 (olivgrön)
- Text-transform: UPPERCASE
- Font-size: 14px
- Margin-bottom: 12px

**Länkgrupp (8 kategorier):**
- Hundfoder
- Kattfoder
- Hästfoder
- Hönsfoder
- Kanin & Marsvin
- Vilt
- Vildfåglar
- Planteringsjord

**Styling (samma som Navigation):**
- Länk-färg: #847949 (olivgrön)
- Hover: #cbbdbd (brunbeige) + underline
- Font-size: 14px
- Spacing mellan links: 8px

### KOLUMN 3: CUSTOMER CARE / SUPPORT

**Rubrik:** "Kundsupport" eller "Customer Care"
- Font: Bold
- Färg: #847949 (olivgrön)
- Text-transform: UPPERCASE
- Font-size: 14px
- Margin-bottom: 12px

**Länkgrupp:**
- FAQ
- Skicka/Returns Info
- Shipping Information
- Kontakta support
- Integritetspolicy
- Användarvillkor

**Styling (samma som Shop):**
- Länk-färg: #847949 (olivgrön)
- Hover: #cbbdbd (brunbeige) + underline
- Font-size: 14px

### KOLUMN 4: KONTAKT INFO

**Rubrik:** "Kontakt"
- Font: Bold
- Färg: #847949 (olivgrön)
- Text-transform: UPPERCASE
- Font-size: 14px
- Margin-bottom: 12px

**Innehåll:**

```
Gläntan
Gläntan 123
960 24 Harads
Sverige

info@glantan.com (clickable mailto:)
070-123 45 67 (clickable tel:)

Öppettider:
Mån-Fre: 10:00 - 18:00
Lör: 10:00 - 14:00
Sön: Stängt
```

**Text styling:**
- Adress text: #574444 (brun), 14px, normal-case (NOT uppercase)
- Email/Phone: #847949 (olivgrön), 14px, clickable (tel: och mailto:)
- Öppettider: Mindre text (#574444), 12px, non-uppercase

### SOCIAL MEDIA / IKONER (Optional, i Kolumn 4 eller separat rad)

**Ikoner:**
- Instagram (@glantan eller motsvarande)
- Facebook (Gläntan Gårdsbutik eller motsvarande)
- (Lägg INTE till för många - bara relevanta sociala kanaler)

**Styling:**
- Ikon-färg: #847949 (olivgrön)
- Hover-färg: #cbbdbd (brunbeige)
- Ikon-storlek: 24px × 24px
- Spacing mellan ikoner: 12px
- Margin-top: 12px från contact info

### BOTTOM BAR / COPYRIGHT SEKTION

**Layout:** Centered, single-line på desktop (eller stacked på mobil)

**Text:**
```
© 2025 Gläntan | Alla rättigheter förbehållna
```

**Styling:**
- Bakgrund: Samma #f8f6f6
- Text-färg: #574444 (brun)
- Font-size: 12px
- Text-transform: uppercase (ordet "Alla", men inte resten)
- Letter-spacing: Subtil
- Margin-top: 32px (avstånd från content ovan)
- Border-top: 1px solid #ede8e8 (beige)
- Padding: 24px 16px

**Länkgrupp i Copyright (Optional):**
- Integritetspolicy (Privacy Policy)
- Användarvillkor (Terms of Service)
- Om kakor (Cookie Settings) - om relevant

### TYPOGRAFI

**Primär Font:**
- Rubrikernas font: Cormorant Garamond, Bold (samma som Astro)
- Body text font: System font (Arial, sans-serif)

**Typografi detaljer:**
- H3 (rubrik): 14px, bold, uppercase, letter-spacing 0.05em
- Links: 14px, regular, letter-spacing 0
- Body text: 12-14px, regular
- Contact info: 14px, regular, normal-case (INTE uppercase)

### RESPONSIVE DESIGN

**Desktop (1024px+):**
- 4 kolumner grid
- Full width layout
- Social media ikoner i kontakt-kolumnen
- Single-line copyright bar

**Tablet (768px - 1024px):**
- 2 kolumner grid
- Navigation + Shop i första raden
- Support + Contact i andra raden
- Copyright full-width under

**Mobil (375px - 768px):**
- 1 kolumn (stacked vertikalt)
- Kolumner stackade i denna ordning:
  1. Navigation
  2. Shop kategorier
  3. Customer Care
  4. Contact Info
  5. Social Media (om applicerbar)
- Copyright full-width under
- Padding: 16px
- Margins mellan kolumner: 24px vertikalt

### SPACING & PADDING

**Desktop:**
- Padding runt footer: 40px 24px
- Gap mellan kolumner: 32px horisontalt
- Gap mellan rader (om applicable): 24px vertikalt

**Tablet:**
- Padding runt footer: 32px 20px
- Gap mellan kolumner: 24px

**Mobil:**
- Padding runt footer: 24px 16px
- Margin mellan sektioner: 24px

### FÄRGREFERENS - COPYPASTA

```
Olivgrön (primär, headings): #847949
Champagne (bakgrund): #f8f6f6
Beige (borders): #ede8e8
Brunbeige (hover): #cbbdbd
Brun (text): #574444
```

### STYLING DETALJER

**Borders/Dividers:**
- Top border på copyright: 1px solid #ede8e8
- Inget border mellan kolumner på desktop

**Shadows:**
- Optional: Subtil top-shadow (inset shadow) för att separera från main content
- Example: `box-shadow: 0 -2px 4px rgba(0,0,0,0.05) inset`

**Hover States:**
- Alla links: Color change + underline on hover
- Transition time: 0.2-0.3s
- No box-shadow eller scale - bara color + underline

**Accessibility:**
- Alla ikoner ska ha aria-labels
- Links ska ha focus-states (outline 2px solid #847949)
- Contact links (tel:, mailto:) ska vara funktionella
- Kontrastkrav uppfyllda (#847949 på #f8f6f6 ✓)

### LINKS - LÄNKA TILL RÄTT STÄLLEN

**Navigation:**
- Hem → /
- Butik → /collections
- Om oss → /pages/about (eller motsvarande)
- Kontakt → /pages/contact (eller motsvarande)

**Shop Kategorier (Peka till Shopify Collections):**
- Hundfoder → /collections/hund
- Kattfoder → /collections/katt
- Hästfoder → /collections/hast
- Hönsfoder → /collections/hons
- Kanin & Marsvin → /collections/kanin-marsvin
- Vilt → /collections/vilt
- Vildfåglar → /collections/vildfaglar
- Planteringsjord → /collections/planteringsjord

**Contact Info (Clickable):**
- Email: mailto:info@glantan.com
- Phone: tel:+46701234567

---

## EXTRA KRAV - MATCH ASTRO DESIGN

1. **Samma färgschema** - Måste matcha exakt
2. **Elegant & minimalistisk** - Inte för muito spacing
3. **Gårdsbutik-känsla** - Varmt, naturligt, lokal autenticitet
4. **Typografi** - Cormorant Garamond för rubriker
5. **No generic template feel** - Ska kännas customized för Gläntan

---

## FINAL OUTPUT KRAV

- **Format:** HTML + Inline CSS (eller Shopify Liquid)
- **Responsive:** Testa på 1920px (desktop), 768px (tablet), 375px (mobil)
- **Interaktivitet:** Alla links clickable, hover-states tydliga
- **Accessibility:** WCAG 2.1 AA compliance minimum
- **Performance:** Ingen bloat - clean, semantic HTML

---

## KONTEXT - ASTRO FOOTER REFERENS

Din Astro-footer (som detta ska spegla) har:
- Champagne bakgrund (#f8f6f6)
- Olivgröna rubriker och links (#847949)
- 4 kolumner på desktop (Navigation, Contact, Info section)
- Logo/brand info i en sektion
- Copyright bar längst ned
- Social media ikoner (Instagram, Facebook)
- Elegant, minimalistisk design
- Clickable contact info (tel:, mailto:)
- Responsive grid layout

---

**Instruktion:** Ge denna prompt direkt till Shopify AI och be om komplett footer-kod i HTML/Liquid format som kan implementeras direkt i Shopify Dawn-temat.

**Önskat output-format:**
"Ge mig komplett footer-kod i HTML/Liquid som är responsive och kan implementeras direkt i Shopify Dawn-temat."
