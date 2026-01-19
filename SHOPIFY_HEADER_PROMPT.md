# Shopify AI Header Prompt - Gläntan Gårdsbutik

Kopiera och klistra in denna prompt direkt i Shopify AI eller din AI-assistent:

---

## PROMPT:

Du ska designa en header för en Shopify Dawn-tema butik som heter "Gläntan" (en gårdsbutik för djurfoder i Harads, Sverige).

### DESIGN KRAV:

**Visual Style (Matcha denna exakt):**
- Bakgrundsfärg: #f8f6f6 (champagne - mycket ljust beige)
- Logo/Text färg: #847949 (olivgrön - varm brun-grön)
- Text (meny-länkar): #574444 (brun - för body text)
- Hover färg: #cbbdbd (brunbeige - för interaktiva element)
- Knapp färg: #847949 (olivgrön - samma som logo)

**Logo:**
- Text: "Gläntan" (eller visa logotyp om den finns)
- Typsnitt: Cormorant Garamond (elegant serif-font), BOLD
- Storlek: 40px höjd i normal state
- Färg: #847949 (olivgrön)

**Navigation Layout:**
- Horisontell meny (desktop)
- Hamburger menu (mobil)
- Länkar: Hem, Sortiment/Shop, Kontakt, Om oss (eller motsvarande)
- Länk-färg: #574444 (brun)
- Länk hover: #847949 (olivgrön) med underline

**Elements i headern:**
1. Logo/Wordmark (vänster sida)
2. Navigation-meny (mitten/höger)
3. Sök-ikon (höger)
4. Varukorg-ikon (höger, med counter)
5. Account/Konto-ikon (höger)

**Color Scheme för ikoner:**
- Sök, Varukorg, Konto: #847949 (olivgrön)
- Hover: #cbbdbd (brunbeige)

**Responsive Behavior:**
- Desktop: Visa full horisontell meny + ikoner
- Tablet: Visa komprimerad meny + ikoner
- Mobil: Hamburger menu (3 streck) + sök + varukorg
- Meny-ikoner: Minst 44px för touch-targets på mobil

**Sticky Behavior (Opcional, men önskvärt):**
- Header ska kunna vara sticky/fixed på scroll
- Vid scroll kan höjden minska från 80px till 60px (smooth transition)
- Logo ska automatiskt skala ned proportionellt (från 40px till 30px)

**Typografi:**
- Rubrik (Logo): Cormorant Garamond Bold, 40px
- Meny-text: System font (Arial, Helvetica, eller sans-serif), 16px
- Letter-spacing: 0.05em för rubriken

**Spacing/Padding:**
- Padding runt content: 16px (mobil) till 24px (desktop)
- Logo margin-right: 40px
- Mellan meny-items: 24px
- Icons spacing: 16px mellan ikoner

**Accessibility:**
- Alla ikoner ska ha aria-labels
- Meny-items ska ha keyboard navigation
- Focus-states ska synas tydligt (outline 2px solid #847949)
- Skip-to-content länk (om möjligt)

**NO-GO's (Gör INTE detta):**
- Använd INTE teal/turkos färger (standarden för Dawn)
- Använd INTE ljusgrå bakgrund - måste vara #f8f6f6
- Använd INTE enkelt sans-serif för logo - måste vara Cormorant Garamond
- Använd INTE för mycket spacing - ska vara compact och elegant

### REFERENS - Din Astro-header ser ut så här:
- Samma färger och typografi
- Logo skalerar när du scrollar
- Elegant, minimalistisk design
- Champagne-bakgrund med olivgröna accenter
- Gårdsbutik-känsla (varmt, elegant, naturligt)

---

**OUTPUT KRAV:**
- Leverera komplett HTML + Inline CSS (eller Liquid för Shopify)
- Eller: Detaljerad kod-beskrivning som kan implementeras i Dawn-temat
- Inkludera responsive design (mobile-first)
- Testa att det fungerar på: Desktop (1920px), Tablet (768px), Mobil (375px)

---

## EXTRA KONTEXT:

**Om Gläntan:**
- Familjeägd gårdsbutik i Harads, Sverige
- Säljer djurfoder för hundar, katter, hästar, höns, kaniner, etc.
- Denna webbshop är för e-handel (plus fysisk butik)
- Målgrupp: Lokala kunder + turister (t.ex. från Treehotel)

**Design Philosophy:**
- Varmt och välkomnande
- Naturkänsla (gård, djur, natur)
- Elegant men inte prestentiös
- Lokal autenticitet

---

**Kopia av färgkoderna för enkelt reference:**
```
Olivgrön (primär): #847949
Champagne (bakgrund): #f8f6f6
Beige (accenter): #ede8e8
Brunbeige (hover): #cbbdbd
Brun (text): #574444
```

**Typsnitt:**
```
Cormorant Garamond (Google Fonts)
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300..700;1,300..700&display=swap');
```

---

**Skriv av och ge denna prompt direkt till Shopify AI, ChatGPT, Claude, eller din AI-assistent.**

**Önskat output-format:** "Ge mig komplett HTML/Liquid-kod som kan implementeras direkt i en Shopify Dawn-tema."
