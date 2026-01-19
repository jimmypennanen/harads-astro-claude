# Gläntan Shopify Design Specification
## Complete Design Guide for Dawn Theme Customization

**Store URL:** https://glantan-2.myshopify.com
**Theme:** Dawn (customized)
**Status:** Pre-launch design review
**Last Updated:** 2026-01-19

---

## 1. Design System Overview

### Brand Colors (Must Match Astro Site)
```
Primary Colors:
- Olive (Primary Brand): #847949
- Champagne (Light Background): #f8f6f6
- Beige (Light Accent): #ede8e8
- Brown-Beige (Secondary Accent): #cbbdbd
- Brown (Text/Dark Accent): #574444

Secondary:
- Forest (Optional): #778c72
- White (Pure): #ffffff
```

**Current Shopify Default (MUST CHANGE):**
- Teal Button Color: #008060 (needs to change to #847949 olive)
- Dark Text: #212b36 (acceptable, but verify brown #574444 is used for warmth)
- Grays: #c4cdd5, #6c6c6c (needs warm brown tints)

### Typography
```
Font Family (Match Astro): Cormorant Garamond, serif
- Headings: Cormorant Garamond Bold, 300-700 weight range
- Body Text: System font or sans-serif for readability
- Size Scale: H1 (32-40px), H2 (28px), H3 (20-24px), Body (16px)
```

---

## 2. Component Design Specifications

### 2.1 Header/Navigation
**Current Issue:** Likely using default Shopify header
**Required Changes:**
- Logo: Use Gläntan wordmark (match Astro header)
- Logo Height: 40px (not 80px) in normal state
- Background Color: #f8f6f6 (champagne)
- Text Color: #847949 (olive)
- Button Color: #847949 (olive) not teal
- Cart Icon: Olive color (#847949)
- Border/Shadow: Subtle line-bottom if any
- Mobile: Hamburger menu in olive
- Sticky Behavior: Should match Astro's scroll behavior

**CSS to Override:**
```css
.header {
  background-color: #f8f6f6;
  border-bottom: 1px solid #ede8e8;
}

.header__heading {
  color: #847949;
}

.header__menu-item a {
  color: #574444;
}

.header__menu-item a:hover {
  color: #847949;
}

.cart-icon,
.menu-icon {
  color: #847949;
}

button[aria-label*="cart"] {
  background-color: #847949;
  color: white;
}

button[aria-label*="cart"]:hover {
  background-color: #cbbdbd;
}
```

### 2.2 Product Cards
**Current Issue:** Likely using default Shopify product card styling
**Required Changes (Match Astro "Utvalda produkter" design):**

```
Layout:
- Background: #ffffff (white)
- Shadow: box-shadow: 0 1px 3px rgba(0,0,0,0.1)
- Border-radius: 8px
- Padding: 16px (inside card)
- Image Container: #f8f6f6 (champagne background), 16px padding

Image:
- Size: 100% width, 160px height min
- Object-fit: cover
- Border-radius: 6px
- Hover effect: scale 1.05, transition 300ms

Title:
- Font: Cormorant Garamond Bold
- Size: 18px
- Color: #847949 (olive)
- Text-transform: uppercase
- Margin: 12px 0 8px

Description:
- Font: System font
- Size: 14px
- Color: #574444 (brown)
- Margin: 8px 0 12px

Price:
- Font: System font Bold
- Size: 16px
- Color: #574444 (brown)
- Margin: 12px 0

Button:
- Style: Solid background
- Background: #847949 (olive)
- Text: #ffffff (white)
- Padding: 12px 24px
- Border-radius: 6px
- Text: uppercase, 12px, bold
- Hover: background #cbbdbd (brown-beige)
- Width: 100%
- Font: System font
```

**HTML Pattern:**
```html
<div class="product-card">
  <div class="product-card__image-wrapper">
    <img src="..." alt="..." class="product-card__image">
  </div>
  <div class="product-card__content">
    <h3 class="product-card__title">Product Name</h3>
    <p class="product-card__description">Short description</p>
    <p class="product-card__price">Price</p>
    <button class="product-card__button">Add to Cart</button>
  </div>
</div>
```

### 2.3 Product Page (Individual Product)
**Current Issue:** Product pages likely need complete redesign
**Required Layout:**

```
Hero Section:
- Two-column layout (image left, details right) on desktop
- Stacked on mobile
- Image: Large, 400-500px, with zoom on hover
- Background: #f8f6f6 (champagne)

Product Details Section:
- Title: H1, Cormorant Garamond, 32px, uppercase, #847949
- Price: 24px, bold, #574444
- Description: 16px, #574444, line-height 1.6
- SKU/ID: 12px, gray, optional
- Rating: If available, 14px, #847949

Add to Cart Section:
- Quantity selector: minimal design
- Size selector: If applicable
- Add to Cart button: Full width, #847949, white text
- Secondary buttons: "Add to wishlist", "Share"

Related Products:
- Grid: 4 columns desktop, 2 mobile
- Same card design as product cards above
```

### 2.4 Collection Pages (Category Pages)
**Current Issue:** Need to ensure categories match Astro shop.astro categories
**Required Sections:**

```
Hero/Banner:
- Background image (category specific)
- Title: Collection name (uppercase)
- Subtitle: Optional description
- Background: Can use semi-transparent overlay
- Text color: white or dark depending on image

Filters Sidebar (Desktop):
- Background: #f8f6f6 (champagne)
- Title: "Filter by" in olive (#847949)
- Filter items: checkbox, 14px, #574444
- Hover: text color to #847949
- Applied filters: Show clearly with X to remove

Products Grid:
- Columns: 4 on desktop, 2 on tablet, 1 on mobile
- Gap: 16px
- Uses same product card design as 2.2

Pagination/Load More:
- Button: #847949 background, white text
- Text: "Load more" or numbered pagination
- Style: Centered, 16px text
```

**Collections Needed (Match Astro shop.astro):**
1. Hund (Dog)
2. Katt (Cat)
3. Häst (Horse)
4. Höns (Chickens)
5. Kanin & Marsvin (Rabbit & Guinea Pig)
6. Vilt (Wildlife/Game)
7. Vildfåglar (Wild Birds)
8. Planteringsjord (Potting Soil)

### 2.5 Cart Page
**Required Design:**

```
Layout:
- Two-column: Cart items (left 2/3), Summary (right 1/3)
- Stacked on mobile

Cart Items:
- Each item in horizontal card
- Image thumbnail: 80px × 80px
- Title: 16px, #847949
- Price: 14px, #574444
- Quantity: Input selector
- Remove link: "Remove" in olive, small text

Cart Summary:
- Background: #f8f6f6 (champagne)
- Padding: 20px
- Subtotal: #574444
- Shipping: #574444
- Tax: #574444
- Total: Bold, 18px, #847949
- Checkout button: Full width, #847949, white text, 44px height
- Continue shopping link: Text link in olive

Empty Cart Message:
- Centered text: "Your cart is empty"
- "Continue shopping" link in olive
```

### 2.6 Checkout Flow
**Must-Have:**
- Background: white or very light champagne
- Text: #574444 (brown)
- Headings: #847949 (olive)
- Buttons: #847949 (olive), white text
- Inputs: Border #ede8e8 (beige), focus border #847949
- Progress indicator: Steps in olive
- Security badges: Bottom of page
- Mobile-optimized: Single column, large touch targets

### 2.7 Footer
**Current Issue:** Likely default Shopify footer
**Required Changes:**

```
Layout (Desktop):
- 4 columns: About, Shop, Customer Care, Contact
- Background: #f8f6f6 (champagne)
- Border-top: 1px solid #ede8e8
- Padding: 40px 20px 20px

Column 1 - About:
- Heading: "Om Gläntan" (#847949)
- Text: "Familjeägd gårdsbutik i Harads..."
- Logo: Optional

Column 2 - Shop:
- Heading: "Handla" (#847949)
- Links: (all categories, text #574444)
  - Hundfoder
  - Kattfoder
  - Hästfoder
  - etc.

Column 3 - Customer Care:
- Heading: "Kundsupport" (#847949)
- Links: (text #574444)
  - FAQ
  - Shipping Info
  - Returns
  - Contact Us

Column 4 - Contact:
- Heading: "Kontakt" (#847949)
- Adress: "Gläntan 123, 960 24 Harads"
- Phone: "070-123 45 67" (clickable tel: link)
- Email: "info@glantan.com" (clickable mailto: link)
- Hours: "Mån-Fre 10-18, Lör 10-14"

Bottom Bar:
- Centered copyright text: "© 2025 Gläntan. All rights reserved."
- Payment icons (if applicable)
- Back to top link (right aligned)
```

### 2.8 Form Elements
**All Forms (Search, Contact, Newsletter, etc.):**

```
Input Fields:
- Border: 1px solid #ede8e8 (beige)
- Background: white
- Padding: 10px 12px
- Font: 14px, #574444
- Border-radius: 4px
- Focus: border-color #847949, box-shadow none

Labels:
- Font: 14px bold, #847949
- Margin-bottom: 6px

Placeholders:
- Color: #6c6c6c (gray, readable but muted)

Select Elements:
- Same styling as inputs
- Arrow: #847949

Buttons (Primary):
- Background: #847949 (olive)
- Text: white, 14px, bold, uppercase
- Padding: 12px 24px
- Border-radius: 4px
- Cursor: pointer
- Hover: background #cbbdbd

Buttons (Secondary):
- Background: white
- Border: 2px solid #847949
- Text: #847949
- Hover: background #f8f6f6

Buttons (Danger/Delete):
- Background: #c4675c (red, if needed)
- Text: white
```

---

## 3. Page-by-Page Implementation Checklist

### 3.1 Homepage
- [ ] Hero banner with background image
- [ ] 3-column collection grid (like Astro shop.astro)
- [ ] Featured products section (4 columns)
- [ ] CTA section ("How to shop" or benefits)
- [ ] Footer with all sections
- [ ] Header with proper styling
- [ ] Mobile responsive (verified)

### 3.2 Product Pages
- [ ] Large product image with zoom
- [ ] Product title (uppercase, olive)
- [ ] Price display
- [ ] Description/details
- [ ] Add to cart button (full width)
- [ ] Quantity selector
- [ ] Related products (4 items)
- [ ] Mobile responsive
- [ ] Breadcrumb navigation

### 3.3 Collection Pages
- [ ] Collection hero/title
- [ ] Filter sidebar (desktop)
- [ ] Product grid (4 cols desktop, 2 tablet)
- [ ] Pagination/load more
- [ ] Sort options (price, newest, etc.)
- [ ] Empty state if no products
- [ ] Mobile: filters accessible via button/modal
- [ ] Breadcrumb navigation

### 3.4 Cart Page
- [ ] Cart items list with images
- [ ] Quantity adjusters
- [ ] Remove item links
- [ ] Cart summary (right sidebar on desktop)
- [ ] Subtotal, tax, total clearly shown
- [ ] Checkout button (primary CTA)
- [ ] "Continue shopping" link
- [ ] Empty cart state
- [ ] Mobile responsive

### 3.5 Checkout
- [ ] Progress indicator (steps)
- [ ] Shipping address form
- [ ] Billing address option
- [ ] Shipping method selector
- [ ] Payment method selector
- [ ] Order summary (right sidebar or bottom)
- [ ] Security badges
- [ ] Mobile optimized

### 3.6 Footer
- [ ] 4-column layout (desktop)
- [ ] About section with store info
- [ ] Shop/categories links
- [ ] Customer care links
- [ ] Contact info (address, phone, email)
- [ ] Copyright/legal links
- [ ] Mobile: collapsible sections
- [ ] Correct background color (#f8f6f6)

---

## 4. CSS Customization Guide

### 4.1 Color Override Priority

**File:** `theme.liquid` or custom CSS file

```css
/* Primary Color Overrides */
:root {
  --color-olive: #847949;
  --color-champagne: #f8f6f6;
  --color-beige: #ede8e8;
  --color-brown-beige: #cbbdbd;
  --color-brown: #574444;
}

/* Remove/override default teal */
.button,
button,
[type="button"],
[type="submit"] {
  background-color: #847949 !important;
  border-color: #847949 !important;
  color: white !important;
}

.button:hover,
button:hover {
  background-color: #cbbdbd !important;
  border-color: #cbbdbd !important;
}

.button--secondary,
button.secondary {
  background-color: transparent !important;
  border: 2px solid #847949 !important;
  color: #847949 !important;
}

.button--secondary:hover {
  background-color: #f8f6f6 !important;
  color: #847949 !important;
}

/* Link styling */
a {
  color: #847949;
}

a:hover {
  color: #cbbdbd;
}

/* Form focus states */
input:focus,
select:focus,
textarea:focus {
  border-color: #847949 !important;
  outline: none;
  box-shadow: 0 0 0 2px rgba(132, 121, 73, 0.1) !important;
}
```

### 4.2 Typography Override

```css
/* Import Cormorant Garamond */
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&display=swap');

/* Headings */
h1, h2, h3, h4, h5, h6,
.h1, .h2, .h3, .h4, .h5, .h6 {
  font-family: 'Cormorant Garamond', serif;
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

h1, .h1 {
  font-size: 2.5rem;
  line-height: 1.2;
}

h2, .h2 {
  font-size: 2rem;
  line-height: 1.3;
}

h3, .h3 {
  font-size: 1.5rem;
  line-height: 1.4;
}

/* Body text */
body {
  font-size: 16px;
  line-height: 1.6;
  color: #574444;
}

p {
  color: #574444;
}
```

### 4.3 Component-Specific CSS

#### Product Cards
```css
.product-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.product-card:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.product-card__image-wrapper {
  background: #f8f6f6;
  padding: 16px;
  overflow: hidden;
  aspect-ratio: 1;
}

.product-card__image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 6px;
  transition: transform 0.3s ease;
}

.product-card:hover .product-card__image {
  transform: scale(1.05);
}

.product-card__title {
  color: #847949;
  text-transform: uppercase;
  font-size: 18px;
  font-weight: 600;
  margin: 12px 0 8px;
}

.product-card__button {
  width: 100%;
  background: #847949;
  color: white;
  padding: 12px 24px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-weight: 600;
  text-transform: uppercase;
  font-size: 12px;
}

.product-card__button:hover {
  background: #cbbdbd;
}
```

#### Collection Grid
```css
.collection-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
  margin-bottom: 40px;
}

@media (max-width: 1024px) {
  .collection-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .collection-grid {
    grid-template-columns: 1fr;
  }
}
```

---

## 5. Mobile Responsiveness Requirements

### 5.1 Breakpoints to Test
- Mobile (320px - 480px)
- Tablet (480px - 1024px)
- Desktop (1024px+)

### 5.2 Mobile-Specific Changes
```
Header:
- Logo: 30px height
- Menu: Hamburger icon (olive)
- Search: Icon only (hide text)

Product Cards:
- Full width on mobile
- Image height: 200px
- Padding: 12px
- Font sizes: Slightly reduced

Checkout:
- Single column layout
- Large touch targets (44px minimum)
- Full-width inputs
- Stack payment options vertically

Footer:
- Collapsible sections
- Single column
- Contact info: clickable links (tel:, mailto:)
```

---

## 6. Testing Checklist (Pre-Launch)

### 6.1 Visual Testing
- [ ] All brand colors match Astro site (screenshot comparison)
- [ ] Typography matches (Cormorant Garamond for headings)
- [ ] Button hover states work and show correct color
- [ ] Product cards display correctly in all breakpoints
- [ ] Collection grid responsive (4→2→1 columns)
- [ ] Images load and display at correct aspect ratios
- [ ] Shadows/depths consistent across all components
- [ ] Spacing/padding consistent (8px increments)

### 6.2 Functional Testing
- [ ] Add to cart button works
- [ ] Cart counter updates
- [ ] Product filters work (if applicable)
- [ ] Sort options work
- [ ] Search functionality works
- [ ] Forms submit correctly
- [ ] Links navigate correctly
- [ ] All collection pages accessible

### 6.3 Mobile Testing
- [ ] Test on iPhone 12/13 (390px width)
- [ ] Test on iPad (768px width)
- [ ] Test on Android (360px width)
- [ ] Hamburger menu works
- [ ] Touch targets at least 44px × 44px
- [ ] Horizontal scrolling doesn't occur
- [ ] Images load on mobile
- [ ] Checkout works on mobile

### 6.4 Browser Testing
- [ ] Chrome (latest)
- [ ] Safari (latest)
- [ ] Firefox (latest)
- [ ] Edge (latest)
- [ ] Mobile Safari (iOS)
- [ ] Chrome Mobile (Android)

### 6.5 Performance
- [ ] Page load < 3 seconds (desktop)
- [ ] First contentful paint < 1.5s
- [ ] Images optimized (WebP where possible)
- [ ] CSS minified
- [ ] No console errors

### 6.6 SEO/Metadata
- [ ] Page titles unique and descriptive
- [ ] Meta descriptions present
- [ ] Open Graph tags on collections
- [ ] Alt text on all product images
- [ ] Structured data (Product schema) on product pages
- [ ] Robots.txt configured
- [ ] Sitemap.xml present

---

## 7. Shopify Liquid Template Modifications

### 7.1 Product Template (product.liquid)
**Key modifications needed:**
1. Hero image section: Change background color to #f8f6f6
2. Product title: Add text-transform: uppercase, font-family Cormorant Garamond
3. Add to cart button: Change color to #847949, add hover state #cbbdbd
4. Product grid: Ensure 4 columns on desktop, 2 on tablet
5. Related products: Use same card styling

### 7.2 Collection Template (collection.liquid)
**Key modifications:**
1. Collection hero: Match design spec
2. Filter sidebar: Style with champagne background
3. Product grid: Use CSS grid with proper gaps
4. Pagination: Use proper Shopify pagination with olive buttons

### 7.3 Cart Template (cart.liquid)
**Key modifications:**
1. Cart items: Horizontal layout with proper spacing
2. Summary: Right sidebar on desktop, moved to bottom on mobile
3. Checkout button: Full width, olive color
4. Empty state: Centered message with link to shop

---

## 8. Color Palette Quick Reference

| Element | Color | Hex | Usage |
|---------|-------|-----|-------|
| Primary Button | Olive | #847949 | CTA buttons, links, accents |
| Secondary Button | Brown-Beige | #cbbdbd | Hover states, secondary actions |
| Background (Light) | Champagne | #f8f6f6 | Card backgrounds, sections |
| Background (Lighter) | Beige | #ede8e8 | Input borders, dividers |
| Text (Primary) | Brown | #574444 | Body text, descriptions |
| Text (Headings) | Olive | #847949 | Headings, titles |
| White | White | #ffffff | Pure white, card backgrounds |
| Accent (Optional) | Forest | #778c72 | Borders, dividers (if needed) |

---

## 9. Before/After Comparison

### Currently in Shopify Default:
- ❌ Teal buttons (#008060)
- ❌ Generic gray colors
- ❌ Default sans-serif fonts
- ❌ Minimal spacing/hierarchy

### After Implementation:
- ✅ Olive buttons (#847949)
- ✅ Warm color palette (champagne, brown, olive)
- ✅ Cormorant Garamond headings
- ✅ Consistent spacing and visual hierarchy
- ✅ Matches Astro site aesthetic
- ✅ Professional gårdsbutik feel

---

## 10. Implementation Priority

### Phase 1 (Critical - Must do first)
1. Override button colors (teal → olive)
2. Override form input colors and styling
3. Update primary typography (add Cormorant Garamond)
4. Fix header/footer colors

### Phase 2 (High - Product pages)
1. Product card design
2. Product page layout
3. Product images styling
4. Add to cart button

### Phase 3 (Medium - Collections & UX)
1. Collection page layout
2. Product grid styling
3. Filter sidebar design
4. Pagination

### Phase 4 (Polish - Final touches)
1. Checkout design
2. Cart page polish
3. Mobile responsiveness verification
4. Performance optimization

---

## 11. Links to Update (When Complete)

In Astro site (when Shopify fully deployed):
- `/src/pages/index.astro`: Replace `SHOPIFY_URL` placeholders
- `/src/pages/shop.astro`: Replace `SHOPIFY_URL` placeholders
- Point to: `https://glantan-2.myshopify.com/collections/{category-slug}`

Example final URLs:
```
https://glantan-2.myshopify.com/collections/hund
https://glantan-2.myshopify.com/collections/katt
https://glantan-2.myshopify.com/products/valpfoder
etc.
```

---

## 12. Next Steps

1. **Access Shopify Admin:**
   - Go to https://glantan-2.myshopify.com/admin
   - Navigate to Theme settings or Custom CSS

2. **Apply CSS customizations:**
   - Add color overrides to theme CSS
   - Verify each change in preview

3. **Modify Liquid templates:**
   - Access theme editor
   - Edit product.liquid, collection.liquid, cart.liquid
   - Test each template with sample products

4. **Create collections:**
   - Hund, Katt, Häst, Höns, Kanin & Marsvin, Vilt, Vildfåglar, Planteringsjord
   - Add placeholder products to test design

5. **Test design:**
   - Check all pages against this specification
   - Test mobile responsiveness
   - Verify all colors, fonts, buttons

6. **Final review:**
   - Screenshot comparison (Astro vs Shopify)
   - Cross-browser testing
   - Mobile device testing

---

**Document Status:** Ready for implementation
**Questions/Issues:** Create tasks below as needed
