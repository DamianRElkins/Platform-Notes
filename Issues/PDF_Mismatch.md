# PDF calc mismatch between Klere and Oneclick

Lendlease gave us numbers we converted unit -> kg then kg/unit -> GBP

Our output number is 20x their number

We are using CF x M to get pdf/gbp, this includes entire supply chain

One Click uses sum of direct impacts, making product, transporting it to you, and installing the product

- this truncates the supply chain at materials, exiobase includes way more in this

# One Click LCA (A1–A5) — process-based approach

**Question being asked:**  
What are the environmental impacts of the **specific physical processes** required to produce and install the materials used in this building?

---

## A1 — Raw material supply

What is the impact of extracting the raw materials?

Includes:

- extraction of minerals, aggregates, metals, timber
- energy used in extraction
- direct emissions from extraction
- processing of raw materials into basic inputs (e.g., cement clinker, steel billets)

Usually based on:

- EPD datasets
- process LCA databases

---

## A2 — Transport of raw materials

What is the impact of transporting raw materials to manufacturing facilities?

Includes:

- fuel use for transport
- emissions from transport
- assumed transport distances
- assumed transport modes (truck, ship, rail)

---

## A3 — Manufacturing

What is the impact of processing raw materials into construction products?

Includes:

- energy used in factories
- process emissions
- processing operations
- packaging
- manufacturing waste

Examples:

- cement production
- steel rolling
- glass manufacturing
- insulation production

---

## A4 — Transport to site

What is the impact of transporting finished construction products to the building site?

Includes:

- truck transport of products
- assumed delivery distances
- fuel use and transport emissions

---

## A5 — Construction / installation

What is the impact of installing the products on site?

Includes:

- construction machinery use
- diesel use on site
- electricity use on site
- material losses and waste
- disposal of packaging
- construction site activities

---

# EXIOBASE + IMPACT World+ — MRIO supply-chain approach

**Question being asked:**  
What are the environmental impacts of **all global economic activity required to produce the goods and services purchased**?

Instead of modelling specific processes, it captures the **entire economic supply chain triggered by spending**.

---

## Raw material production (analogous to A1)

Impact includes not only mining itself, but the entire upstream economy required to support it.

Examples:

- mining operations
- energy used in mining
- chemical inputs used in mining
- manufacturing of mining equipment
- maintenance of machinery
- production of spare parts
- transportation services used by mining companies
- business services supporting mining

---

## Transport of raw materials (analogous to A2)

Impact includes the full supply chain of transportation.

Examples:

- fuel combustion for transport
- refining and distribution of fuel
- extraction of crude oil
- production of transport vehicles
- maintenance of transport vehicles
- supporting logistics services

---

## Material processing and manufacturing (analogous to A3)

Impact includes the full upstream supply chain required for manufacturing.

Examples:

- factory energy use
- industrial fuel supply chains
- upstream material inputs
- chemical production
- equipment manufacturing
- industrial maintenance
- utilities used by factories

---

## Transport to construction site (analogous to A4)

If transportation is included in spending, impacts include:

- transport activity
- fuel supply chains
- vehicle supply chains
- logistics services

---

## Construction and installation activities (analogous to A5)

If construction-sector spending is included, impacts include:

- construction equipment fuel
- electricity used on site
- production of construction equipment
- upstream supply chains supporting construction services

---

# Key structural difference

### One Click

- **process-based LCA**
- models **specific construction processes**
- based on **material quantities**
- supply chains are **limited to known inputs**

### EXIOBASE + IMPACT World+

- **economic input-output model**
- models **entire global supply chains**
- based on **economic spending**
- captures **all indirect upstream activity**

---

# Simplified comparison

**One Click asks:**

> What happened physically to produce and install the materials in this building?

**EXIOBASE asks:**

> What global economic activity occurred because money was spent to produce these materials and services?

---

# Consequence

Because EXIOBASE captures **much deeper supply chains**, it often estimates **larger total impacts** than process-based A1–A5 calculations.
Compare this with using CF x S which is direct impact ~10-15x less than CF x M

Options:

Explain the reasoning behind the difference (would need to look more closely into this)
Use the CF x S multipliers for pdf and label it as direct impact (lessens our value pitch)
Use both CF x S and CF x M multipliers and show direct and full supply chain
