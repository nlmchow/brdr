# HKMA BRDR Search Project

This repository provides a **vanilla setup** for an AI-powered search experience built on **Google Vertex AI Search**, designed to explore the **Hong Kong Monetary Authority (HKMA) Banking Research and Data Repository (BRDR)**. It is live on https://nlmchow.github.io/brdr/ host using GitHub Pages

It includes:

- A **UI** for interacting with Vertex AI Search (`docs/index.html`)

## 🔍 Advanced Features You Can Explore

The vanilla setup provided in this repository implements a basic **retrieve** → **serve** → **answer generation** pipeline.
If you choose to configure your own setup, Google Vertex AI Search offers advanced capabilities that can enhance your search experience:

**Prepare Stage**

Normalizes the input query, identifies the search context, and routes it to the correct fulfillment pipeline.

**Synonyms**

Expand queries by adding custom synonyms.
Example: Searching for "CAR" could also return results for "Capital Adequacy Ratio."

**Autocomplete**

Predict and suggest possible search queries based on the user’s partial input.

**Retrieve Stage**

Finds the most relevant documents from your data, using context gathered in the Prepare stage.

**Data Store**

The configured dataset or index for retrieval. You can set up ingestion workflows here.
(Click to configure ingestion in Vertex AI Search console)

**Signal Stage**

Ranks retrieved content by applying rules, criteria, and ranking algorithms before serving results.

**Boost/Bury**

Promote or demote results based on categorical, numerical, or date attributes.
Example: Boost newer reports or bury outdated ones.

**Filter**

Narrow down retrieved items by specific constraints (e.g., author, date range, category).

**Signal Viewer**

Inspect and re-rank results based on various relevance signals.

**Serve Stage**

Provides the output to the user.

**Answer Generation**

Configure and customize AI-generated answers with specific tone, style, and content grounding.
Example: Generate concise executive summaries or detailed analytical responses.

Tip: These advanced features can be configured in the Vertex AI Search Console once your own custom pipelines are deployed.
Integrating them can significantly improve search accuracy and user experience.

---

## 📂 Repository Structure

docs/
└── index.html # Basic web UI to access Vertex AI Search

## ⚙️ Requirements

* Google Cloud Platform (GCP) account
* Vertex AI Search enabled
* Terraform (>= 1.3)
* Access to HKMA BRDR public content
* GitHub

## ⚠️ Constraints and Limitations

- **Vertex AI Search does not support `.doc` file ingestion**  
  The HKMA BRDR dataset in this repository contains approximately **22 files** in `.doc` format.  
  These files **cannot be indexed** directly in Vertex AI Search.
  
## 🔒 Notes

* This is a vanilla deployment for quick setup — security and tuning are needed for production use.
* Handle BRDR data according to HKMA's terms of use and relevant regulations.

## TODO

- **Terraform scripts** to provision required Google Cloud resources
- Scripts to **upload BRDR documents** from HKMA into the search index
