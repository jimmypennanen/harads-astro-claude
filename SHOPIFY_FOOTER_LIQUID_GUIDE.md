# Shopify Footer Implementation Guide - Gläntan Edition

Om du föredrar att implementera footern själv eller vill veta exakt hur det fungerar.

## ALTERNATIV 1: Använd Shopify AI (Enklast)

Kopiera prompten från `SHOPIFY_FOOTER_PROMPT.md` och ge den till Shopify AI:
1. Kopiera allt innehål efter "## PROMPT:"
2. Gå till Shopify AI
3. Klistra in och fråga om footer-kod
4. Få färdig, responsive footer!

---

## ALTERNATIV 2: Manuell Implementation i Shopify Theme Editor

### Steg 1: Hitta footer-filen

1. Gå till **Online Store → Themes → Customize**
2. Klicka på **Edit code**
3. Sök efter: **sections/footer.liquid**
4. (Om den inte finns, kan du också lägga CSS i **assets/custom.css**)

### Steg 2: Ändra footer-templatens CSS

I **assets/custom.css** (eller inline i footer-filen), lägg till:

```css
/* ============================================
   GLÄNTAN FOOTER CUSTOMIZATION
   ============================================ */

footer {
  background-color: #f8f6f6 !important;
  color: #847949 !important;
  padding: 40px 24px !important;
}

footer h3,
footer h2 {
  color: #847949 !important;
  font-weight: 700 !important;
  text-transform: uppercase !important;
  letter-spacing: 0.05em !important;
  font-size: 14px !important;
  margin-bottom: 12px !important;
}

footer a {
  color: #847949 !important;
  text-decoration: none !important;
  transition: all 0.2s ease !important;
}

footer a:hover {
  color: #cbbdbd !important;
  text-decoration: underline !important;
}

footer ul,
footer li {
  list-style: none !important;
  margin: 0 !important;
  padding: 0 !important;
}

footer li {
  margin-bottom: 8px !important;
}

footer p {
  color: #574444 !important;
  font-size: 14px !important;
  margin-bottom: 4px !important;
}

/* Grid Layout */
.footer-content {
  display: grid !important;
  grid-template-columns: repeat(4, 1fr) !important;
  gap: 32px !important;
  margin-bottom: 32px !important;
}

.footer-column h3 {
  margin-bottom: 12px !important;
}

.footer-column ul li {
  margin-bottom: 8px !important;
}

/* Contact Info */
.footer-contact {
  font-style: normal !important;
}

.footer-contact p {
  font-size: 14px !important;
  color: #574444 !important;
  margin-bottom: 8px !important;
}

.footer-contact a {
  display: inline !important;
  color: #847949 !important;
}

/* Social Icons */
.footer-social {
  display: flex !important;
  gap: 12px !important;
  margin-top: 12px !important;
}

.footer-social a {
  display: inline-flex !important;
  align-items: center !important;
  justify-content: center !important;
  width: 24px !important;
  height: 24px !important;
}

.footer-social svg {
  width: 24px !important;
  height: 24px !important;
  fill: #847949 !important;
  transition: fill 0.2s ease !important;
}

.footer-social a:hover svg {
  fill: #cbbdbd !important;
}

/* Copyright Bar */
.footer-copyright {
  border-top: 1px solid #ede8e8 !important;
  padding-top: 24px !important;
  text-align: center !important;
  color: #574444 !important;
  font-size: 12px !important;
  text-transform: uppercase !important;
}

/* Responsive */
@media (max-width: 1024px) {
  .footer-content {
    grid-template-columns: repeat(2, 1fr) !important;
    gap: 24px !important;
  }
}

@media (max-width: 768px) {
  footer {
    padding: 24px 16px !important;
  }

  .footer-content {
    grid-template-columns: 1fr !important;
    gap: 24px !important;
  }

  .footer-copyright {
    font-size: 11px !important;
    padding-top: 20px !important;
  }
}
```

### Steg 3: Ändra footer.liquid template

Här är en basic struktur du kan klistra in:

```liquid
<footer class="site-footer">
  <div class="max-w-7xl mx-auto px-6">

    <div class="footer-content">

      <!-- Column 1: Navigation -->
      <div class="footer-column">
        <h3>Navigation</h3>
        <ul>
          <li><a href="/">Hem</a></li>
          <li><a href="/collections">Butik</a></li>
          <li><a href="/pages/om-oss">Om oss</a></li>
          <li><a href="/pages/kontakt">Kontakt</a></li>
        </ul>
      </div>

      <!-- Column 2: Shop Categories -->
      <div class="footer-column">
        <h3>Handla</h3>
        <ul>
          <li><a href="/collections/hund">Hundfoder</a></li>
          <li><a href="/collections/katt">Kattfoder</a></li>
          <li><a href="/collections/hast">Hästfoder</a></li>
          <li><a href="/collections/hons">Hönsfoder</a></li>
          <li><a href="/collections/kanin-marsvin">Kanin & Marsvin</a></li>
          <li><a href="/collections/vilt">Vilt</a></li>
          <li><a href="/collections/vildfaglar">Vildfåglar</a></li>
          <li><a href="/collections/planteringsjord">Planteringsjord</a></li>
        </ul>
      </div>

      <!-- Column 3: Customer Care -->
      <div class="footer-column">
        <h3>Kundsupport</h3>
        <ul>
          <li><a href="/pages/faq">FAQ</a></li>
          <li><a href="/pages/shipping">Fraktkostnad</a></li>
          <li><a href="/pages/returns">Returner</a></li>
          <li><a href="/pages/kontakt">Kontakta support</a></li>
          <li><a href="/pages/privacy">Integritetspolicy</a></li>
          <li><a href="/pages/terms">Användarvillkor</a></li>
        </ul>
      </div>

      <!-- Column 4: Contact Info -->
      <div class="footer-column">
        <h3>Kontakt</h3>
        <div class="footer-contact">
          <p><strong>Gläntan</strong></p>
          <p>Gläntan 123</p>
          <p>960 24 Harads</p>
          <p>Sverige</p>

          <p style="margin-top: 12px;">
            <a href="mailto:info@glantan.com">info@glantan.com</a>
          </p>
          <p>
            <a href="tel:+46701234567">070-123 45 67</a>
          </p>

          <p style="margin-top: 12px; font-size: 12px;">
            <strong>Öppettider:</strong><br>
            Mån-Fre: 10:00 - 18:00<br>
            Lör: 10:00 - 14:00<br>
            Sön: Stängt
          </p>

          <!-- Social Media Icons -->
          <div class="footer-social">
            <a href="https://instagram.com/glantan" target="_blank" aria-label="Instagram">
              <svg viewBox="0 0 24 24">
                <path d="M7.75 2C4.7 2 2 4.7 2 7.75v8.5C2 19.3 4.7 22 7.75 22h8.5C19.3 22 22 19.3 22 16.25v-8.5C22 4.7 19.3 2 16.25 2h-8.5zM12 7.5A4.5 4.5 0 1 1 7.5 12 4.5 4.5 0 0 1 12 7.5zm0 7.5a3 3 0 1 0-3-3 3 3 0 0 0 3 3zm5.5-8.2a1.3 1.3 0 1 1-1.3-1.3 1.3 1.3 0 0 1 1.3 1.3z"/>
              </svg>
            </a>
            <a href="https://facebook.com/glantan" target="_blank" aria-label="Facebook">
              <svg viewBox="0 0 24 24">
                <path d="M22.67 0H1.33C.6 0 0 .6 0 1.33v21.33C0 23.4.6 24 1.33 24h11.5v-9.33H9.77v-3.64h3.06V8.4c0-3 1.8-4.67 4.53-4.67 1.31 0 2.69.23 2.69.23v2.97h-1.52c-1.5 0-1.96.94-1.96 1.9v2.28h3.33l-.53 3.64h-2.8V24h5.49c.73 0 1.33-.6 1.33-1.33V1.33C24 .6 23.4 0 22.67 0z"/>
              </svg>
            </a>
          </div>
        </div>
      </div>

    </div>

    <!-- Copyright Bar -->
    <div class="footer-copyright">
      <p>&copy; 2025 Gläntan | Alla rättigheter förbehållna</p>
    </div>

  </div>
</footer>
```

---

## ALTERNATIV 3: Skapa Custom Footer Section

Om du vill total kontroll, kan du skapa en helt ny footer-section:

### 1. Skapa fil: `sections/footer-glanten.liquid`

```liquid
<style>
  .glanten-footer {
    background-color: #f8f6f6;
    padding: 40px 24px;
  }

  .glanten-footer__content {
    max-width: 1280px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 32px;
    margin-bottom: 32px;
  }

  .glanten-footer__column h3 {
    color: #847949;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    font-size: 14px;
    margin-bottom: 12px;
  }

  .glanten-footer__column ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .glanten-footer__column li {
    margin-bottom: 8px;
  }

  .glanten-footer__column a {
    color: #847949;
    text-decoration: none;
    transition: all 0.2s ease;
  }

  .glanten-footer__column a:hover {
    color: #cbbdbd;
    text-decoration: underline;
  }

  .glanten-footer__contact p {
    color: #574444;
    font-size: 14px;
    margin-bottom: 8px;
  }

  .glanten-footer__social {
    display: flex;
    gap: 12px;
    margin-top: 12px;
  }

  .glanten-footer__social a svg {
    width: 24px;
    height: 24px;
    fill: #847949;
    transition: fill 0.2s ease;
  }

  .glanten-footer__social a:hover svg {
    fill: #cbbdbd;
  }

  .glanten-footer__copyright {
    border-top: 1px solid #ede8e8;
    padding-top: 24px;
    text-align: center;
    color: #574444;
    font-size: 12px;
    text-transform: uppercase;
  }

  @media (max-width: 1024px) {
    .glanten-footer__content {
      grid-template-columns: repeat(2, 1fr);
      gap: 24px;
    }
  }

  @media (max-width: 768px) {
    .glanten-footer {
      padding: 24px 16px;
    }

    .glanten-footer__content {
      grid-template-columns: 1fr;
      gap: 24px;
    }
  }
</style>

<footer class="glanten-footer">
  <div class="glanten-footer__content">
    <!-- Navigation -->
    <div class="glanten-footer__column">
      <h3>Navigation</h3>
      <ul>
        <li><a href="/">Hem</a></li>
        <li><a href="/collections">Butik</a></li>
        <li><a href="/pages/om-oss">Om oss</a></li>
        <li><a href="/pages/kontakt">Kontakt</a></li>
      </ul>
    </div>

    <!-- Shop -->
    <div class="glanten-footer__column">
      <h3>Handla</h3>
      <ul>
        <li><a href="/collections/hund">Hundfoder</a></li>
        <li><a href="/collections/katt">Kattfoder</a></li>
        <li><a href="/collections/hast">Hästfoder</a></li>
        <li><a href="/collections/hons">Hönsfoder</a></li>
        <li><a href="/collections/kanin-marsvin">Kanin & Marsvin</a></li>
        <li><a href="/collections/vilt">Vilt</a></li>
        <li><a href="/collections/vildfaglar">Vildfåglar</a></li>
        <li><a href="/collections/planteringsjord">Planteringsjord</a></li>
      </ul>
    </div>

    <!-- Customer Care -->
    <div class="glanten-footer__column">
      <h3>Kundsupport</h3>
      <ul>
        <li><a href="/pages/faq">FAQ</a></li>
        <li><a href="/pages/shipping">Frakt</a></li>
        <li><a href="/pages/returns">Returner</a></li>
        <li><a href="/pages/kontakt">Kontakta support</a></li>
        <li><a href="/pages/privacy">Integritetspolicy</a></li>
        <li><a href="/pages/terms">Användarvillkor</a></li>
      </ul>
    </div>

    <!-- Contact -->
    <div class="glanten-footer__column">
      <h3>Kontakt</h3>
      <div class="glanten-footer__contact">
        <p><strong>Gläntan</strong></p>
        <p>Gläntan 123</p>
        <p>960 24 Harads</p>
        <p>Sverige</p>

        <p style="margin-top: 12px;">
          <a href="mailto:info@glantan.com">info@glantan.com</a>
        </p>
        <p>
          <a href="tel:+46701234567">070-123 45 67</a>
        </p>

        <p style="margin-top: 12px; font-size: 12px;">
          <strong>Öppettider:</strong><br>
          Mån-Fre: 10:00 - 18:00<br>
          Lör: 10:00 - 14:00<br>
          Sön: Stängt
        </p>

        <!-- Social -->
        <div class="glanten-footer__social">
          <a href="https://instagram.com/glantan" target="_blank" aria-label="Instagram">
            <svg viewBox="0 0 24 24">
              <path d="M7.75 2C4.7 2 2 4.7 2 7.75v8.5C2 19.3 4.7 22 7.75 22h8.5C19.3 22 22 19.3 22 16.25v-8.5C22 4.7 19.3 2 16.25 2h-8.5zM12 7.5A4.5 4.5 0 1 1 7.5 12 4.5 4.5 0 0 1 12 7.5zm0 7.5a3 3 0 1 0-3-3 3 3 0 0 0 3 3zm5.5-8.2a1.3 1.3 0 1 1-1.3-1.3 1.3 1.3 0 0 1 1.3 1.3z"/>
            </svg>
          </a>
          <a href="https://facebook.com/glantan" target="_blank" aria-label="Facebook">
            <svg viewBox="0 0 24 24">
              <path d="M22.67 0H1.33C.6 0 0 .6 0 1.33v21.33C0 23.4.6 24 1.33 24h11.5v-9.33H9.77v-3.64h3.06V8.4c0-3 1.8-4.67 4.53-4.67 1.31 0 2.69.23 2.69.23v2.97h-1.52c-1.5 0-1.96.94-1.96 1.9v2.28h3.33l-.53 3.64h-2.8V24h5.49c.73 0 1.33-.6 1.33-1.33V1.33C24 .6 23.4 0 22.67 0z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- Copyright -->
  <div class="glanten-footer__copyright">
    <p>&copy; 2025 Gläntan | Alla rättigheter förbehållna</p>
  </div>
</footer>
```

---

## FÄRGER - KOPIERA & KLISTRA

```css
:root {
  --color-olive: #847949;
  --color-champagne: #f8f6f6;
  --color-beige: #ede8e8;
  --color-brown-beige: #cbbdbd;
  --color-brown: #574444;
}
```

---

## TESTA FOOTERN

**Desktop (1920px):**
- ✅ 4 kolumner visas
- ✅ Bakgrund är #f8f6f6
- ✅ Rubriker är olivgröna (#847949)
- ✅ Links blir brunbeige (#cbbdbd) vid hover

**Tablet (768px):**
- ✅ 2 kolumner
- ✅ Layout är responsive

**Mobil (375px):**
- ✅ 1 kolumn (stacked)
- ✅ All text läsbar
- ✅ Links clickable
- ✅ Social ikoner synliga

---

## NÄSTA STEG

1. **Implementera footer** (välj Alternativ 1, 2, eller 3)
2. **Spara och testa** i Shopify
3. **Jämför med Astro-footer** - se att designen matchar
4. **Testa på mobil** - se att det ser bra ut
5. **Lås den** så den inte förändras av temuppdateringar

---

## BEHÖVER DU HJÄLP?

- **Alternativ 1 (Shopify AI):** Kopiera promten från `SHOPIFY_FOOTER_PROMPT.md`
- **Alternativ 2 (Manuell CSS):** Följ stegen ovan
- **Alternativ 3 (Custom Section):** Kopiera koden ovan

Väl lyckat!
