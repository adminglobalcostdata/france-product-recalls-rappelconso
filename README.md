# France Product Recalls RappelConso: 19,216 notices

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-1f6feb)](https://apify.com/phonic_lily/france-product-recalls-rappelconso) ![Licence](https://img.shields.io/badge/licence-Licence_Ouverte_v2.0-blue) ![Records](https://img.shields.io/badge/records-19%2C311-green)

Search 19,216 French consumer product recall notices from RappelConso (DGCCRF, DGAL, DGEC, DGPR): brand, GTIN barcodes, batches, reason, risks, distributors, consumer actions and official notice links. Embedded data, pay per record.

## What you get
- **19,311 records**, each carrying its own `license` and `attribution` fields, ready to republish with the required credit.
- A **100-record free sample** in this repository: [`sample.jsonl`](sample.jsonl) and [`sample.csv`](sample.csv) (opens as a table on GitHub).
- The **full dataset** as a filterable API (JSON, CSV, Excel), no scraping, no login: [France Product Recalls RappelConso: 19,216 notices on Apify](https://apify.com/phonic_lily/france-product-recalls-rappelconso).

## One record
```json
{
  "recall_id": "24137",
  "notice_number": null,
  "version": 1,
  "published_at": "2026-11-23T10:25:14+01:00",
  "published_date": "2026-11-23",
  "legal_nature": "volontaire (sans arrêté préfectoral)",
  "category": "alimentation",
  "subcategory": "viandes",
  "brand": "le foué paul prédault",
  "title": "jambon cuit supérieur braisé aux légumes le foué paul prédault",
  "models_or_references": "jambon cuit supérieur braisé aux légumes le foué paul prédault",
  "product_identification": "3177340010499$6160142345$date limite de consommation$2026-12-25$"
}
```

## Quick start
Python:
```python
from apify_client import ApifyClient
client = ApifyClient('<YOUR_APIFY_TOKEN>')
run = client.actor('phonic_lily/france-product-recalls-rappelconso').call(run_input={'maxResults': 10})
for item in client.dataset(run['defaultDatasetId']).iterate_items():
    print(item)
```
Or from the command line:
```bash
curl -X POST 'https://api.apify.com/v2/acts/phonic_lily~france-product-recalls-rappelconso/run-sync-get-dataset-items?token=<YOUR_APIFY_TOKEN>' \
  -H 'Content-Type: application/json' -d '{"maxResults": 10}'
```
Pricing is pay-per-record on Apify (see the Actor page); the sample here is free.

## Fields
| Field | Description |
|---|---|
| `recall_id` | RappelConso recall id (stable). |
| `notice_number` | Recall notice number, for example 2026-11-0060. |
| `version` | Notice version number. |
| `published_at` | Publication date-time (ISO 8601, UTC). |
| `published_date` | Publication date, YYYY-MM-DD. |
| `legal_nature` | Legal nature of the recall (voluntary, prefectoral order...). Null on old notices. |
| `category` | Product category (alimentation, automobiles, ...). |
| `subcategory` | Product sub-category. |
| `brand` | Product brand. |
| `title` | Recall title (product label). |
| `models_or_references` | Models or references concerned. |
| `product_identification` | Raw identification lines: GTIN, batch, expiry or best-before date, separated by /. |
| `gtins` | GTIN barcodes extracted from the identification lines, semicolon separated. |
| `gtin_count` | Number of GTINs, null when none is given. |
| `packaging` | Packaging. |
| `sale_start_date` | Start of marketing, ISO date. |
| `sale_end_date` | End of marketing, ISO date. |
| `storage_temperature` | Storage temperature statement. |
| `health_mark` | Health mark (food). |
| `additional_information` | Additional information. |
| `sale_area` | Geographic sale area. |
| `distributors` | Distributors (companies). |
| `reason` | Reason for the recall. |
| `risks` | Risks incurred. |
| `health_recommendations` | Health recommendations. |
| `risk_description` | Additional description of the risk. |
| `consumer_actions` | Actions to be taken by the consumer, separated by /. |
| `compensation` | Compensation terms. |
| `recall_procedure_end_date` | End date of the recall procedure, ISO date. |
| `public_information` | Public additional information. |
| `image_urls` | Image URLs, separated by /. |
| `product_list_url` | URL of the list of products. |
| `distributor_list_url` | URL of the list of distributors. |
| `poster_pdf_url` | URL of the PDF recall poster. |
| `notice_url` | URL of the official notice on rappel.conso.gouv.fr. |
| `license` | Licence of the data. |
| `attribution` | Required attribution text. |

## Data, licence and attribution
RappelConso V2 dataset 'rappelconso-v2-gtin-espaces' on data.economie.gouv.fr (https://data.economie.gouv.fr/explore/dataset/rappelconso-v2-gtin-espaces/), published by the French consumer-protection and food-safety authorities under Licence Ouverte v2.0 (Etalab): the licence page of the dataset reads 'Licence Ouverte v2.0 (Etalab)'. Licence terms: free reuse, including commercial, provided the source and the date of last update are mentioned. Export taken on 2026-11-09 (19,216 notices, latest published 2026-11-09). Text is kept as published (the source lower-cases most values). The consumer-service telephone number column is NOT included. Null means the source gives no value; it is never 0.

**Licence:** Licence Ouverte v2.0 (Etalab)

**Attribution:** Source: RappelConso V2, DGCCRF, DGAL, DGEC and DGPR, data.economie.gouv.fr, Licence Ouverte v2.0 (Etalab), https://www.etalab.gouv.fr/licence-ouverte-open-licence/. Data retrieved 2026-11-09.

Snapshot date: 2026-11-25. Empty values are `null`, never 0.

## Cite this dataset
GitHub's *Cite this repository* button reads [`CITATION.cff`](CITATION.cff).

## Feedback
Found an error or want a field added? Open an issue in this repository.
