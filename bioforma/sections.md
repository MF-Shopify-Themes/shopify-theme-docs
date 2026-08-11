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

#### 🧪 Product Ingredients Matrix (Dual-Engine Dynamic Fallback)

La sezione **Product Ingredients Matrix** è progettata con un'architettura ibrida avanzata. Offre due metodi indipendenti per inserire i componenti attivi, i dosaggi e le funzioni cliniche, bilanciando l'estrema facilità d'uso nel Customizer con la portabilità totale dei dati del catalogo tramite esportazione in file CSV.

Il codice del tema controlla automaticamente la presenza di dati nel database del prodotto; se il database è vuoto, scala istantaneamente sul layout grafico dei blocchi nativi.

##### 🔹 Opzione A: Gestione Visiva tramite Blocchi Nativi (Metodo Rapido)
Ideale per cataloghi ridotti o per un setup istantaneo senza configurazioni esterne al codice del tema.
1. Apri lo **Shopify Theme Editor (Personalizza)** e naviga sulla pagina di un Prodotto.
2. Nel pannello di sinistra, clicca su **Aggiungi sezione** e seleziona **Product Ingredients**.
3. Sotto la sezione appena creata, clicca su **Aggiungi blocco** (Aggiungi Ingrediente).
4. Compila direttamente i tre campi grafici visivi nel pannello:
   - *Ingredient Name*: Il nome scientifico del composto (es. `Suntheanine® L-Theanine`).
   - *Clinical Dosage*: La quantità esatta (es. `200 mg`).
   - *Biological Function*: La descrizione dell'azione biochimica (es. `Aumenta l'attività delle onde cerebrali alfa`).
5. Puoi trascinare, riordinare o eliminare i blocchi liberamente. I dati verranno salvati esclusivamente nel layout del template di quella pagina.

##### 🔸 Opzione B: Gestione tramite Metafield JSON (Metodo Avanzato e Portabile via CSV)
Raccomandato per store con molteplici referenze e formule uniche. Questo approccio lega i dati chimici direttamente alla scheda del singolo prodotto nel database di Shopify, permettendo di esportare e reimportare tutto massivamente tramite file CSV senza perdere le informazioni.

**Fase 1: Registrazione del Canale nel Database**
*(Operazione da eseguire una sola volta per l'intero store)*
1. Dal pannello di controllo principale di Shopify, vai su **Impostazioni (Settings)** → **Dati personalizzati (Custom Data)** → **Prodotti (Products)**.
2. Clicca su **Aggiungi definizione** e compila rigorosamente i seguenti campi:
   - **Nome**: `Ingredients List`
   - **Spazio dei nomi e chiave**: `bioforma.ingredients_list`
   - **Tipo**: Cambia la selezione impostando **Valore singolo** e poi **Testo su più righe** (Multi-line text).
3. Clicca su **Salva**.

**Fase 2: Connessione nel Theme Editor**
1. Apri il **Theme Editor**, seleziona la sezione *Product Ingredients* a sinistra.
2. Posizionati sopra il campo **Ingredients JSON** e fai clic sull'icona rotonda del **Vettore Dinamico (Dynamic Source)** (il foglietto con il simbolo `+`).
3. Seleziona dalla lista la voce **Ingredients List** appena creata e clicca su **Salva**.

**Fase 3: Inserimento dei Dati Molecolari Strutturati**
1. Vai nella scheda del prodotto reale nel pannello di amministrazione di Shopify e scorri la pagina fino in fondo.
2. Troverai la casella vuota del metafield `Ingredients List`.
3. Incolla all'interno dell'area di testo la struttura JSON dettagliata seguendo questo pattern sintattico rigido a prova di errore:

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
4. Salva la scheda del prodotto. Il tema rileverà la stringa, scompatterà l'array in memoria e sostituirà l'avviso di onboarding con la griglia asimmetrica a CLS: 0.00.

### 📄 Customizing Other Pages

You can also add sections to your **About Us**, **FAQ**, or **Blog** pages to create a cohesive design across your entire website. 

### 💡 How to Add a Section

1. Navigate to the page you want to edit using the top dropdown menu in the Theme Editor.
2. In the left sidebar, scroll to the bottom of the section list and click **Add section**.
3. Choose a section from the list.
4. Drag the section using the ⋮⋮ icon to change its vertical position on the page.

[⬅️ Back to BioForma Index](./index.md)
