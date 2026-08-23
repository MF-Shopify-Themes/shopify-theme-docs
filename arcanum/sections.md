---
layout: default
title: Arcanum Sections, Blocks & Features
---

<a id="table-of-contents"></a>
### 🧩 Arcanum Sections, Blocks & Architectural Features

Arcanum leverages Shopify's Online Store 2.0 architecture, empowering merchants to construct rich, atmospheric storefronts using drag-and-drop sections and modular blocks.

---

### 📌 Table of Contents

* 🔮 [Native Metafield Filtering (Intention, Chakra, Zodiac)](#metaphysical-filtering)
* 📦 [Hybrid Product Page (Physical + Digital + Services)](#hybrid-product-page)
  * 🃏 [Interactive 3D Tarot & Oracle Deck Inspector (`<tarot-deck-viewer>`)](#tarot-viewer)
  * 💎 [Crystal & Gemstone Safety Matrix](#crystal-safety-matrix)
  * 🌿 [Botanical Herbalism & Apothecary Codex](#botanical-codex)
  * ⚡ [Orgonite & Sacred Geometry Matrix](#orgonite-matrix)
  * 🔮 [Spiritual Readings & Birth Chart Booking Forms](#spiritual-services)
* 🔁 [Native Subscription & Mystery Box Widget (`<subscription-selector>`)](#subscription-widget)
* 🕯️ [Ritual Kit & Altar Bundle Builder (`<ritual-bundle-builder>`)](#bundle-builder)
* 📖 [Shoppable Editorial Magazine Blog](#editorial-blog)
* 🌙 [Real-Time Moon Phase & Ephemeris Bar (`<moon-phase-widget>`)](#moon-phase-bar)
* 🛒 [Slide-Out Altar Cart Drawer (`<cart-drawer>`)](#altar-cart-drawer)
* ᛟ [Accessible Runic Text Rendering (`render-runic-text`)](#runic-rendering)
* 🌫️ [Atmospheric Micro-Animations & Moving Mist Canvas](#atmospheric-animations)

---

<a id="metaphysical-filtering"></a>
### 🔮 Native Metafield Filtering (Intention, Chakra, Zodiac)

Arcanum provides native storefront filtering powered by the official **Shopify Search & Discovery** engine without requiring external app subscriptions.

#### Configurable Metaphysical Taxonomies:
* **Spiritual Intention** (`custom.intention`): *Protection, Abundance & Wealth, Love & Attraction, Shadow Work, Banishing, Astral Travel, Intuition & Psychic Opening*.
* **Chakra Correspondence** (`custom.chakra`): *Root (Muladhara), Sacral (Svadhisthana), Solar Plexus (Manipura), Heart (Anahata), Throat (Vishuddha), Third Eye (Ajna), Crown (Sahasrara), Soul Star*.
* **Zodiac Signs** (`custom.zodiac_sign`): *Aries, Taurus, Gemini, Cancer, Leo, Virgo, Libra, Scorpio, Sagittarius, Capricorn, Aquarius, Pisces*.
* **Alchemical Elements** (`custom.element`): *Fire, Water, Air, Earth, Aether/Spirit*.
* **Planetary Rulers** (`custom.planet`): *Sun, Moon, Mercury, Venus, Mars, Jupiter, Saturn*.

#### How to Enable:
1. In Shopify Admin, navigate to **Settings > Custom data > Products** and define the desired Metafield definitions.
2. Open the **Shopify Search & Discovery** app and add these Metafields under **Filters**.
3. In the Theme Editor, open the Collection template and enable **Display Metaphysical Facets**. The theme automatically renders SVG alchemical glyphs and active filter pills with instant AJAX updates.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="hybrid-product-page"></a>
### 📦 Hybrid Product Page (Physical + Digital + Services)

Arcanum natively handles 3 distinct commerce models within a single unified product template:

<a id="tarot-viewer"></a>
#### 🃏 1. Interactive 3D Tarot & Oracle Deck Inspector (`<tarot-deck-viewer>`)
Allows buyers to flip through and inspect high-resolution card artwork before purchasing 78-card tarot or oracle decks.
* **Pure CSS 3D Transforms**: Smooth 180° card-flip revealing upright/reversed keywords, astrological correspondences, and card descriptions without heavy external libraries.
* **Configuration**: Add sample cards via product metafields (`custom.tarot_sample_cards`) or Theme Editor product blocks.

<a id="crystal-safety-matrix"></a>
#### 💎 2. Crystal & Gemstone Safety Matrix
Crucial for mineral and gemstone merchants to provide crystal care guidelines and prevent customer mishaps:
* **Mohs Hardness Badge** (`custom.mohs_hardness`): Displays mineral scratch resistance (1–10).
* **Water-Safe Status** (`custom.water_safety`): Warns if a crystal dissolves or rusts in water (e.g. *Selenite, Malachite*).
* **Sun-Safe Status** (`custom.sun_safety`): Alerts if crystal color fades under direct sunlight (e.g. *Amethyst, Rose Quartz*).
* **Elixir Safety** (`custom.elixir_safety`): Critical safety warning if mineral contains toxic copper/aluminum compounds unsafe for direct gem elixirs.
* **Cleansing Protocols**: Built-in tabs for *Moonlight, Smudging, Sound, Earth, and Selenite Charging*.

<a id="botanical-codex"></a>
#### 🌿 3. Botanical Herbalism & Apothecary Codex
* **Binomial Latin Name** (`custom.botanical_name`): Formats scientific botanical taxonomy (e.g. *Salvia apiana*, *Artemisia vulgaris*).
* **Planetary & Elemental Associations**: Visual tags connecting herbs to ritual planetary rulers.
* **Compliance & Safety Accordion**: Pre-structured disclaimers for ritual vs culinary/topical usage.

<a id="orgonite-matrix"></a>
#### ⚡ 4. Orgonite & Sacred Geometry Matrix
* **Matrix Specifications** (`custom.orgonite_matrix`): Resin-to-metal ratio, piezoelectric quartz core, copper coil tensor rings, and EMF radiation shielding specifications.

<a id="spiritual-services"></a>
#### 🔮 5. Spiritual Readings & Birth Chart Booking Forms
For merchants selling personalized astrology consultations, tarot readings, or spellcraft services:
* **Native Client Intake Block**: Collects client birth date, exact birth time, birth city/country, and reading focus question directly on the product page.
* **Seamless Line-Item Properties**: Data is attached directly to the cart item (`properties[...]`) and sent straight to the Shopify Order Admin.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="subscription-widget"></a>
### 🔁 Native Subscription & Mystery Box Widget (`<subscription-selector>`)

Built specifically for recurring **Monthly Mystery Altar Boxes**, quarterly solstice ritual supplies, and auto-restock incenses.

* **Native Selling Plans API**: Interacts directly with Shopify's native subscription contracts without injecting bulky third-party scripts.
* **Preset-Adaptive UI**: Adapts borders, fonts, and colors to the active theme preset (Dark, Vampire, Runic, Celestial).
* **Incentive Callouts**: Dynamic badge highlighting subscriber discounts (*"Subscribe & Save 15% + Receive Free Consecrated Oil"*).

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="bundle-builder"></a>
### 🕯️ Ritual Kit & Altar Bundle Builder (`<ritual-bundle-builder>`)

An interactive step-by-step altar kit creator that increases Average Order Value (AOV):
* **Step-by-Step Flow**:
  1. *Choose Altar Cloth / Grimoire*
  2. *Choose Ritual Candle Set*
  3. *Choose Botanical Incense / Consecration Oil*
  4. *Choose Focus Crystal / Talisman*
* **Dynamic Bundle Pricing**: Calculates tier discounts in real-time and dispatches all selected variant IDs simultaneously to the Shopify Cart API.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="editorial-blog"></a>
### 📖 Shoppable Editorial Magazine Blog

Metaphysical stores thrive on content-led organic traffic (astrology forecasts, full moon rituals, tarot guidebooks).

* **Grimoire Editorial Layout**: Drop caps, estimated reading time, author alchemical bio, and interactive table of contents.
* **In-Article Shoppable Product Cards (`product-card-inline`)**: Merchants can embed product cards directly inside the article body. Readers can inspect prices and click **Add to Cart** instantly via AJAX without navigating away from the ritual guide.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="moon-phase-bar"></a>
### 🌙 Real-Time Moon Phase & Ephemeris Bar (`<moon-phase-widget>`)

* **Client-Side Mathematical Calculation**: Computes the exact current lunar illumination and zodiac constellation in real-time with zero external API latency (1KB script).
* **Ritual Urgency**: Displays timely ritual recommendations (e.g., *"Full Moon in Scorpio: Ideal for Banishing & Divination"*).

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="altar-cart-drawer"></a>
### 🛒 Slide-Out Altar Cart Drawer (`<cart-drawer>`)

* **Consecration Threshold Bar**: Live visual progress bar for tiered free gifts or free shipping.
* **One-Click Sacred Upsells**: Instant add-ons for altar matches, velvet tarot bags, charcoal disks, and sage smudges.
* **Mobile Sticky Buy Bar**: Sticky bottom buy bar on product pages with instant variant selection.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="runic-rendering"></a>
### ᛟ Accessible Runic Text Rendering (`render-runic-text`)

Every title and heading across the theme is centrally routed through the [`render-runic-text`](file:///c:/personal/shopify/arcanum-theme/snippets/render-runic-text.liquid) snippet:
* When `settings.style_preset == 'runic'`, automatically converts specified latin characters (O, A, T, F, U) into elder futhark runic glyphs (`ᛟ`, `ᚨ`, `ᛏ`, `ᛠ`, `ᚢ`) with hand-carved alternating CSS offsets.
* Encapsulated inside `aria-label` with `aria-hidden="true"` on rune spans to preserve **100% Google SEO indexing and screen-reader accessibility**.
* Other presets (*Dark, Vampire, Celestial*) render pristine unaltered typography.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="atmospheric-animations"></a>
### 🌫️ Atmospheric Micro-Animations & Moving Mist Canvas

Arcanum introduces ambient, immersive micro-animations designed to captivate spiritual buyers while maintaining high-efficiency Lighthouse scores:

* **Amazing Moving Mist Background Animation (`.alchemical-smoke-canvas`)**:
  * Renders a full-viewport procedural volumetric incense mist in the Dark preset.
  * Driven by a native SVG `feTurbulence` filter with continuous SMIL parameter animation (`baseFrequency` morphing cycle), ensuring an uninterrupted living smoke effect across the whole page with zero raster seams and 0 KB network payload.
  * Automatically respects visitor accessibility settings via `@media (prefers-reduced-motion: reduce)`.

* **Moving Glow & Mystic Smoke Edge Card Animations (`.product-card`)**:
  * Collection product cards in the Dark preset are encircled by an **amazing mist and glow animation moving** along the top and side perimeters at 60 FPS.
  * Combines GPU-composited chromatic gradients (`#EB1E91`, `#B5179E`, `#7209B7`, `#3A0CA3`) with SVG displacement distortion (`#alchemical-mystic-smoke`) and cyclical `:nth-child` offsets, creating non-repeating organic energy waves around catalog items without DOM reflow.

[⬆️ Back to Table of Contents](#table-of-contents)
