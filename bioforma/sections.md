### 🧩 BioForma Sections & Layouts

BioForma uses Shopify's Online Store 2.0 architecture, allowing you to add, remove, and reorder drag-and-drop sections on any page of your store. 

To customize your layout, open the Shopify Theme Editor and look at the **Sections tab (Layers icon)** in the left sidebar. 

### 🏠 Homepage Sections

You can build your homepage by stacking standard modular sections: 

* **Hero Banner / Slideshow:** Use high-quality imagery to introduce your main supplement or beauty line with clear Call-to-Action buttons.
* **Featured Collection:** Display a grid of your top-selling products or new nootropic releases.
* **Icon Grid / Brand Benefits:** A row of text and icons to quickly highlight key product claims (e.g., *100% Organic, Laboratory Tested, Made in Italy*).
* **Rich Text / Brand Story:** Share the science or philosophy behind your health and wellness products.

### 📦 Product Page Sections

The product template includes specialized blocks to help convert visitors into customers: 

* **Product Information:** The core block containing the title, price, variant selectors, and the main buy button.
* **Collapsible Tabs:** Perfect for organizing dense information without cluttering the page. Use them for *Ingredients, Supplement Facts, Usage Instructions,* and *Shipping Policy*.
* **Related Products:** Automatically recommend complementary products (e.g., suggesting a beauty cream to match a dietary supplement).

#### 🧪 Product Ingredients Matrix & Supplement Facts Table (Pure Database Architecture)

BioForma includes two 100% database-driven components engineered for scientific transparency and structured data management. Both components automatically ingest structured payload data directly from native Shopify Product Metafields under the `bioforma` namespace.

##### 1. Product Ingredients Matrix (`bioforma.ingredients_list`)
Renders full molecular composition lists via `sections/product-ingredients.liquid`.

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

##### 2. Supplement Facts Table (`bioforma.supplement_facts`)
Renders an interactive nutritional facts table with scientific detail micro-drawers via `snippets/product-supplement-facts.liquid` and the `supplement_facts` Theme Block.

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
2. In the Product section, click **Add block** and select **Supplement facts**.
3. Reorder the block vertically using the drag handle as desired.
4. Click **Save**.

**Step 3: Populating Product Metafield Data**
1. Navigate to any individual Product in Shopify Admin and scroll to the Metafields area.
2. Locate `Supplement Facts` and enter the structured JSON array using the active keys (`name`, `amount`, `daily_value`, `benefits`):

```json
[
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
```

##### 💡 Onboarding Context & Theme Editor Behavior
When no metafield data is detected on an active storefront product page, zero HTML markup is rendered to prevent empty structural containers. However, inside the Shopify Theme Editor (`request.design_mode`), an onboarding dashed container placeholder is rendered strictly for merchant setup guidance.

### 📄 Customizing Other Pages

You can also add sections to your **About Us**, **FAQ**, or **Blog** pages to create a cohesive design across your entire website. 

### 💡 How to Add a Section

1. Navigate to the page you want to edit using the top dropdown menu in the Theme Editor.
2. In the left sidebar, scroll to the bottom of the section list and click **Add section**.
3. Choose a section from the list.
4. Drag the section using the ⋮⋮ icon to change its vertical position on the page.

[⬅️ Back to BioForma Index](./index.md)
