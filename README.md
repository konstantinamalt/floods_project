# Troubled Waters
## The multiple devastating impact of floods across Europe

Troubled Waters is a data-driven research project analyzing flood impact on different leveles across Europe over the past decade by combining satellite data from the Copernicus Emergency Management Service (EMS) with public datasets like Hanze and EM-DAT, revealing the most vulnerable regions and the urgent need for a unified EU disaster database.

## Publication links:
##### Scrolly
- English [here](https://miir.gr/longreads/flood-in-europe-en.html)
- Greek [here](https://miir.gr/longreads/flood-in-europe-gr.html)

##### Articles
- [EFSYN](https://www.efsyn.gr/themata/thema-tis-efsyn/467620_taragmena-nera-o-katastrofikos-antiktypos-ton-plimmyron-stin-eyropi) (GR)
- [MIIR](https://miir.gr/otan-vrechei-akoma-fovamai-oti-to-potami-tha-mas-ta-parei-ola/) (GR)
- [EL CONFIDENCIAL](https://www.elconfidencial.com/mundo/europa/2025-03-31/valencia-tesalia-baja-sajonia-comparan-peores-inundaciones-europa_4096524/) (ES)
- [CIVIO](https://civio.es/medio-ambiente/2025/03/31/la-dana-de-valencia-frente-a-las-grandes-inundaciones-europeas-de-los-ultimos-anos/) (ES)
- [PRESSONE](https://pressone.ro/investigatie-ape-tulburi-impactul-devastator-al-inundatiilor-in-europa]) (RO)

## Project identity and credits
Organised and coordinated by the Mediterranean Institute for Investigative Reporting (MIIR.gr) with the collaboration of the European Data Journalism Network ((EDJNet)[https://www.europeandatajournalism.eu/]).
- Data collection and analysis: Konstantina Maltepioti
- Fact-checking: Eva Lopez ([DW](https://www.dw.com/en/top-stories/s-9097]))
- Research: Kostas Zafeiropoulos (MIIR)
- Scrolly design: Krisztián Szabó (Atlatszo)
- Illustrations: Louisa Karageorgiou

The project was a collaboration of 6 EDJNet members: [MIIR]([https://miir.gr/) (Greece), [Atlatszo](https://atlatszo.hu/) (Hungary), [Facta](https://facta.eu/) (Italy), [El Confidencial](https://www.elconfidencial.com/), [Civio](https://civio.es/) (Spain), [PressOne](https://pressone.ro/) (Romania).

## Objectives
- Identify flood-prone regions in Europe, deaths and population affected over a decade (2014–2024)
- Analyse land, infrastructure, and population affected over the last two years (2023-2024)
- Normalize inconsistent data from multiple sources (Copernicus, Public EM-DAT, Hanze)
- Provide a methodology for Copernicus' satellite data that can be used for othe natural disasters

## Methodology Summary
- Searched for open-access European flood datasets with key indicators (extent, land type, population, infrastructure).
- Selected three main data sources: **Hanze**, **Public EM-DAT**, and **Copernicus EMS**.
- Collected detailed flood data from **Copernicus API** (2023–2024), using unique flood IDs from the "Activations" page.
- Matched Copernicus **AOIs** (Areas of Interest) to official **NUTS 3 regions** using Eurostat and manual search.
- Filtered overlapping AOIs to avoid double counting flooded areas and population.
- Measured flood extent by combining flooded areas and flood traces, excluding permanent water bodies.
- Normalized Copernicus data subcategories creating bigger categories to group data better.
- Excluded inconsistent fields (e.g. residential buildings reported in incompatible units).
- Merged Copernicus data with Hanze and EM-DAT to build a decade-long, region-level flood dataset.
- Created consistent fields across datasets such as: flood ID, date, country, region, typology, population, fatalities, sources.

👉 See **From Space to Spreadsheet: The Troubled Waters Methodology** [here](https://konstantinamalt.github.io/floods/)

You can use the included notebook to extract Copernicus flood data via their API without needing to install Python—simply open it in Google Colab, input your selected flood IDs, and run the script.

Manual methods are also outlined in the documentation for use cases where the API is inaccessible.

### Data Challenges
#### 1. Fragmented & inconsistent data 
Flood data across Europe is fragmented, with no centralized standard. Key indicators, such as flood extent, fatalities, affected population, and infrastructure damage, are often missing, outdated, or reported inconsistently across datasets.
#### 2. Regional mismatch  
Copernicus defines Areas of Interest (AOIs) that do not match official administrative regions. Manual searching and cross-reference with Eurostat’s NUTS 3 classification was required to enable regional comparisons and typologies. Public EM-DAT data also required manual search to adhere to Eurostat's classification of administrative regions. HANZE had the proper names and codes based on Eurostat's classification, but needed to be updated to match the classification of 2024.
#### 3. Overlapping observations  
In Copernicus multiple AOIs often overlap for a single flood event, with repeated observations recorded as separate products. Filtering was required to avoid double counting flood extent, affected land, infrastructure and populations.
#### 4. Inconsistent satellite reporting  
Copernicus summary tables often exclude "flood traces," underreporting the actual flooded area. Manual review of each AOI’s full statistics was necessary to accurately capture total flood extent.
#### 5. Unit inconsistencies  
Satelitte data for infrastructure and buildings were reported using inconsistent units (e.g. hectares vs. number or kilometers), sometimes even within the same flood. To ensure consistency, some categories, like residential buildings, were excluded from final analysis.
#### 6. Coverage gaps  
- **Hanze** and **EM-DAT** lacked any flood extent data. Affected population data were available but still sparse.
- **Hanze** stops recording floods in 2020.
- **EM-DAT** records sharply declined in 2022, raising concerns about underreporting.
- **Copernicus** only tracks floods requested by authorized users, and not all flood occurencies.
#### Evolving APIs and Platforms  
During the project, Copernicus changed its web platform, removing visible access to its open API in newer pages. Though the API remains functional as of May 30 2025, data retrieval using this methogology may require adapting in the future.

## Final Datasets
- Download Copernicus flood impact data (2023-2024)[here](https://github.com/konstantinamalt/floods_project/blob/main/CLEAN_FINAL_aois_all_details_nuts_translated.xlsx), filename: "CLEAN_FINAL_aois_all_details_nuts_translated.xlsx"
- Download Decade dataset from all three sources (2014-2023) [here](https://github.com/konstantinamalt/floods_project/blob/main/decade_final_dataset_copernicus_emdat_hanze.xlsx), filename: "decade_final_dataset_copernicus_emdat_hanze.xlsx"

## Dataset for regions
- Download Eurostat regional data 2021-2024 [here](https://github.com/konstantinamalt/floods_project/blob/main/NUTS2021-NUTS2024(1).xlsx) filename: "NUTS2021-NUTS2024(1).xlsx"

### License & Citation
The data for this project is open for use.


