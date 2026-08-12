<a id="table-of-contents"></a>
### 🧩 BioForma Sections & Layouts

BioForma uses Shopify's Online Store 2.0 architecture, allowing you to add, remove, and reorder drag-and-drop sections on any page of your store. 

To customize your layout, open the Shopify Theme Editor and look at the **Sections tab (Layers icon)** in the left sidebar. 

> [!IMPORTANT]
> ⚡ **Maintain Maximum Storefront Performance**: BioForma includes a native **[High-Performance App Wrapper](#app-wrapper)** to prevent third-party Shopify apps from degrading your page speed. Always wrap heavy app blocks to preserve 90+ Lighthouse mobile performance scores and instant page loads.

---

### 📌 Table of Contents

* 🏠 [Homepage Sections](#homepage-sections)
* 📦 [Product Page Sections](#product-page-sections)
  * 🧪 [Product Ingredients Matrix & Supplement Facts Table](#database-driven-components)
    * 1️⃣ [Product Ingredients Matrix (`bioforma.ingredients_list`)](#ingredients-matrix)
      * 🔹 [Setup & Data Configuration](#ingredients-setup)
      * 🛠️ [Interactive JSON Generator (Ingredients List)](#ingredients-generator-tool)
    * 2️⃣ [Supplement Facts Table (`bioforma.supplement_facts`)](#supplement-facts)
      * 🔹 [Setup & Data Configuration](#supplement-facts-setup)
      * 🛠️ [Interactive JSON Generator (Supplement Facts)](#supplement-facts-generator-tool)
    * 💡 [Onboarding Context & Theme Editor Behavior](#onboarding-behavior)
  * 🔄 [Subscription-First Tiered Pricing (`<product-subscription>`)](#product-subscription)
  * 🖼️ [Zero-CLS Product Gallery & Media (`<product-gallery-thumbnails>`)](#product-gallery)
* 🛒 [Smart AJAX Cart Drawer (`<cart-drawer>`)](#cart-drawer)
* ⚡ [High-Performance App Wrapper (`<high-perf-app-wrapper>`)](#app-wrapper)
* ❓ [Multi-Instance FAQ Search (`<faq-search>`)](#faq-search)
* 📄 [Customizing Other Pages](#customizing-other-pages)
* 💡 [How to Add a Section](#how-to-add-a-section)

---

<a id="homepage-sections"></a>
### 🏠 Homepage Sections

You can build your homepage by stacking standard modular sections: 

* **Hero Banner / Slideshow:** Use high-quality imagery to introduce your main supplement or beauty line with clear Call-to-Action buttons.
* **Featured Collection:** Display a grid of your top-selling products or new nootropic releases.
* **Icon Grid / Brand Benefits:** A row of text and icons to quickly highlight key product claims (e.g., *100% Organic, Laboratory Tested, Made in Italy*).
* **Rich Text / Brand Story:** Share the science or philosophy behind your health and wellness products.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="product-page-sections"></a>
### 📦 Product Page Sections

The product template includes specialized blocks to help convert visitors into customers: 

* **Product Information:** The core block containing the title, price, variant selectors, and the main buy button.
* **Collapsible Tabs:** Perfect for organizing dense information without cluttering the page. Use them for *Ingredients, Supplement Facts, Usage Instructions,* and *Shipping Policy*.
* **Related Products:** Automatically recommend complementary products (e.g., suggesting a beauty cream to match a dietary supplement).

<a id="database-driven-components"></a>
#### 🧪 Product Ingredients Matrix & Supplement Facts Table (Pure Database Architecture)

BioForma includes two 100% database-driven components engineered for scientific transparency and structured data management. Both components automatically ingest structured payload data directly from native Shopify Product Metafields under the `bioforma` namespace.

<a id="ingredients-matrix"></a>
##### 1. Product Ingredients Matrix (`bioforma.ingredients_list`)
Renders full molecular composition lists via `sections/product-ingredients.liquid`.

<a id="ingredients-setup"></a>
###### 🔹 Setup & Data Configuration

**Step 1: Metafield Definition**
*(Perform once for the entire store)*
1. In Shopify Admin, navigate to **Settings** → **Custom Data** → **Products**.
2. Click **Add definition** and configure the fields:
   - **Name**: `Ingredients List`
   - **Namespace and key**: `bioforma.ingredients_list`
   - **Type**: Select **JSON**.
3. Click **Save**.

**Step 2: Connecting in Theme Editor**
1. Open the **Shopify Theme Editor (Customize)** and select the **Product Ingredients** section.
2. Connect the **Ingredients JSON** field to the `Ingredients List` dynamic source.
3. Click **Save**.

**Step 3: Populating Product Metafield Data**
1. Navigate to any individual Product in Shopify Admin and scroll to the Metafields area.
2. Locate `Ingredients List` and enter the structured JSON array using the active keys (`name`, `dosage`, `function`):

```json
[
  {
    "name": "Magnesium Bisglycinate Chelate",
    "dosage": "400 mg",
    "function": "Crosses blood-brain barrier to optimize REM and Slow-Wave deep sleep architecture."
  },
  {
    "name": "Suntheanine® L-Theanine",
    "dosage": "200 mg",
    "function": "Increases alpha brainwave activity for deep relaxation without sedation."
  },
  {
    "name": "Apigenin 98%",
    "dosage": "50 mg",
    "function": "Binds to central benzodiazepine receptors to accelerate sleep latency."
  }
]
```

<a id="ingredients-generator-tool"></a>
###### 🛠️ Interactive JSON Generator (Ingredients List)
Fill out the table below to generate valid JSON automatically. **You can drag and drop rows vertically using the drag handle (`⋮⋮`) to reorder ingredients**. Once all fields are completed, click **Copy JSON to Clipboard** and paste it directly into the product metafield in Shopify Admin:

{% include ingredients-generator.html %}

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="supplement-facts"></a>
##### 2. Supplement Facts Table (`bioforma.supplement_facts`)
Renders an interactive nutritional facts table with scientific detail micro-drawers via `sections/product-supplement-facts.liquid`.

<a id="supplement-facts-setup"></a>
###### 🔹 Setup & Data Configuration

**Step 1: Metafield Definition**
*(Perform once for the entire store)*
1. In Shopify Admin, navigate to **Settings** → **Custom Data** → **Products**.
2. Click **Add definition** and configure the fields:
   - **Name**: `Supplement Facts`
   - **Namespace and key**: `bioforma.supplement_facts`
   - **Type**: Select **JSON**.
3. Click **Save**.

**Step 2: Connecting in Theme Editor**
1. Open the **Shopify Theme Editor (Customize)** on a Product page template.
2. Scroll to the bottom of the section list and click **Add section**.
3. Select **Supplement facts**.
4. Reorder the section vertically using the drag handle (⋮⋮) as desired.
5. Click **Save**.

**Step 3: Populating Product Metafield Data**
1. Navigate to any individual Product in Shopify Admin and scroll to the Metafields area.
2. Locate `Supplement Facts` and enter the structured JSON object with key/value header fields and the `ingredients` array:

```json
{
  "daily_serving": "2 capsules",
  "servings_per_container": "30 (60 capsules)",
  "footnote": "* Reference Intake (NRV) not established. Third-party laboratory certified ultra-pure formula.",
  "ingredients": [
    {
      "name": "NMN (Nicotinamide Mononucleotide)",
      "amount": "500 mg",
      "daily_value": "*",
      "benefits": "Direct high-purity NAD+ precursor. Promotes cellular DNA repair, mitochondrial health, and systemic longevity."
    },
    {
      "name": "Trans-Resveratrol 99%",
      "amount": "250 mg",
      "daily_value": "*",
      "benefits": "Potent antioxidant polyphenol extracted from Polygonum cuspidatum. Activates sirtuins (SIRT1) and optimizes NAD+ efficacy."
    }
  ]
}
```

<a id="supplement-facts-generator-tool"></a>
###### 🛠️ Interactive JSON Generator (Supplement Facts)
Fill out the dosage header fields and ingredients table below to generate valid JSON automatically. **You can drag and drop rows vertically using the drag handle (`⋮⋮`) to reorder ingredients**. Once all fields are completed, click **Copy JSON to Clipboard** and paste it directly into the product metafield in Shopify Admin:

{% include supplement-facts-generator.html %}

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="onboarding-behavior"></a>
##### 💡 Onboarding Context & Theme Editor Behavior
When no metafield data is detected on an active storefront product page, zero HTML markup is rendered to prevent empty structural containers. However, inside the Shopify Theme Editor (`request.design_mode`), an onboarding dashed container placeholder is rendered strictly for merchant setup guidance.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="product-subscription"></a>
#### 🔄 Subscription-First Tiered Pricing (`<product-subscription>`)

Engineered specifically for health, supplement, and recurring wellness brands, BioForma integrates a native `<product-subscription>` custom element (`assets/product-subscription.js`).

* **Dynamic Selling Plan Integration**: Binds natively to Shopify Selling Plans (Subscriptions) and form variant changes without external app overrides.
* **Tiered Volume Discounts**: Automatically calculates volume price reductions (e.g. 10% or 20% savings on 60-day or 90-day supplies) and updates the price display dynamically.
* **Zero Cumulative Layout Shift**: Intercepts variant changes via event-driven hooks (`pointerdown` and `change`) to update prices instantly in ~0.2ms without causing structural reflows.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="product-gallery"></a>
#### 🖼️ Zero-CLS Product Gallery & Media (`<product-gallery-thumbnails>`)

The BioForma product page section (`sections/product.liquid`) features a high-performance thumbnail gallery driven by `assets/product-image-zoom.js`.

* **CSS Scroll Snap Track**: Employs pure CSS horizontal scroll snap for frictionless, native touch navigation on mobile devices.
* **WebP CDN Compression**: Optimized with Shopify CDN WebP filters (`width: 120`, `loading: lazy`, `fetchpriority: low`).
* **Instant DOM Image Swap**: Uses pre-warmed `pointerdown` listeners to trigger instant 60fps main image replacements in ~0.2ms - 0.5ms under CPU throttling.
* **Native Rich Media**: Supports Shopify 3D Interactive Models (.GLB / .USDZ) via `model_viewer_tag` and HTML5 Video via `video_tag` without heavy third-party iframe overlays.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="cart-drawer"></a>
### 🛒 Smart AJAX Cart Drawer (`<cart-drawer>`)

BioForma includes an advanced side-out sliding AJAX cart drawer (`sections/cart-drawer.liquid` & `assets/cart-drawer.js`) engineered to maximize Average Order Value (AOV) and conversion.

* **Dynamic Price Interception**: Automatically syncs with native Shopify subscription selling plans and volume discounts, displaying struck-through original vs. final prices in real-time.
* **Clinical Savings Badge**: Renders a prominent savings indicator (`Saved $X.XX`) dynamically updated based on cart item metadata.
* **Free Shipping Threshold Bar**: Features an active progress indicator tracking remaining amount required to unlock free shipping.
* **Hardware-Accelerated Slide**: 60fps CSS GPU transitions (`will-change: transform, opacity`) ensure smooth side-drawer opening/closing on iOS and Android devices.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="app-wrapper"></a>
### ⚡ High-Performance App Wrapper (`<high-perf-app-wrapper>`)

Third-party Shopify Apps (such as product reviews, loyalty widgets, and cross-sell popups) frequently execute unoptimized JavaScript payloads during initial DOM parsing. This can severely degrade mobile page speed and lower your store's Google Lighthouse score.

BioForma solves this problem natively with the `<high-perf-app-wrapper>` custom element (`snippets/high-performance-app-wrapper.liquid` & `assets/high-performance-app-wrapper.js`).

#### 🚀 Key Features & Optimization Pillars
* **Inert Payload Isolation**: Wraps heavy third-party App Blocks inside native HTML `<template>` elements. This completely hides unoptimized app scripts from initial browser DOM parsing and layout trees.
* **Hardware-Accelerated Dual Hydration**: Deploys a dual-trigger asynchronous engine running `IntersectionObserver` (`rootMargin: "250px 0px"`) alongside `requestIdleCallback` (`timeout: 4000`). App scripts execute only when the user scrolls near the section or during browser idle time, preserving 90+ Lighthouse mobile performance scores.
* **Seamless Customizer Preview**: Automatically detects Shopify Theme Editor (`request.design_mode`) to bypass lazy loading during customization, allowing merchants to configure and preview app widgets in real-time.
* **Zero Cumulative Layout Shift (CLS)**: Reserves layout dimensions (`min-height: 150px`) to lock structural layout shifts at absolute `0.00`.

#### 💡 How to Use
1. In the **Shopify Theme Editor (Customize)**, add any **App Block** (Theme App Extension) inside a supported page section.
2. The BioForma theme shell automatically wraps the app block via `snippets/high-performance-app-wrapper.liquid`.
3. On your live storefront, third-party scripts hydrate seamlessly without slowing down initial page loads or blocking the main rendering thread.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="faq-search"></a>
### ❓ Multi-Instance Live FAQ Search (`<faq-search>`)

The BioForma FAQ section (`sections/faq-search.liquid` & `assets/faq-search.js`) provides zero-latency client-side search filtering designed for clinical clarity.

* **Scoped Multi-Instance Search**: Custom element `<faq-search>` uses strictly scoped DOM queries to isolate search operations per section instance without global ID conflicts.
* **White Clinical Aesthetics**: Minimalist accordion UI built with accessible HTML5 `<details>` and `<summary>` elements with fine dividers and plus-to-close micro-interactions.
* **Zero Layout Jumps (0.00 CLS)**: Hardware-accelerated CSS Grid transitions (`grid-template-rows: 0fr` → `1fr`) lock layout shifts at absolute `0.00` during expand, collapse, and search filtering.

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="customizing-other-pages"></a>
### 📄 Customizing Other Pages

You can also add sections to your **About Us**, **FAQ**, or **Blog** pages to create a cohesive design across your entire website. 

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="how-to-add-a-section"></a>
### 💡 How to Add a Section

1. Navigate to the page you want to edit using the top dropdown menu in the Theme Editor.
2. In the left sidebar, scroll to the bottom of the section list and click **Add section**.
3. Choose a section from the list.
4. Drag the section using the ⋮⋮ icon to change its vertical position on the page.

[⬆️ Back to Table of Contents](#table-of-contents)

---

[⬅️ Back to BioForma Index](./index.md)
