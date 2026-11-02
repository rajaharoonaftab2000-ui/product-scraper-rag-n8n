# Product Scraper & RAG Knowledge Base with n8n

An automated workflow that turns e-commerce product pages into an AI-ready knowledge base using **n8n, Google Gemini embeddings, and Supabase**.

## Overview

Manually collecting product information takes time and makes it difficult to prepare consistent data for AI applications.

This project demonstrates how to collect product links, extract product content, process it into smaller text chunks, and store embeddings in a vector database. The resulting knowledge base provides a foundation for semantic product search and Retrieval-Augmented Generation (RAG) applications.

## What the Workflow Does

- Fetches a source page and prepares product links.
- Processes individual product pages through a loop.
- Extracts and prepares product information.
- Splits content into smaller text chunks.
- Generates embeddings using Google Gemini.
- Stores content, metadata, and embeddings in Supabase.
- Uses wait steps to control processing pace.
- Supports scheduled execution through an n8n Schedule Trigger.

## Workflow Process

1. **Trigger:** Start the workflow on a configured schedule.
2. **Fetch:** Retrieve the source page using an HTTP Request.
3. **Extract Links:** Use HTML extraction and JavaScript to prepare product URLs.
4. **Process Products:** Loop through the product pages and collect their content.
5. **Prepare Content:** Clean and structure the extracted information.
6. **Generate Embeddings:** Split the content and create Google Gemini embeddings.
7. **Store:** Save the processed content and vectors in Supabase.

## Technology Stack

| Tool | Purpose |
|---|---|
| n8n | Workflow orchestration and scheduling |
| HTTP Request nodes | Fetch source and product pages |
| HTML extraction | Extract relevant page content |
| JavaScript | Transform and prepare data |
| Text Splitter | Divide content into manageable chunks |
| Google Gemini embeddings | Convert text into vector representations |
| Supabase Vector Store | Store content, metadata, and embeddings |

## Demo

The demo shows the workflow processing product pages, completing an execution, and saving records in Supabase.

This is a personal portfolio demonstration.

## Business Applications

The stored product knowledge can support:

- Semantic product search.
- Product information retrieval.
- RAG-powered shopping assistants.
- Internal product research tools.
- Customer support knowledge bases.

These applications require an additional retrieval or assistant layer connected to the stored data.

## Setup Requirements

To recreate or adapt this workflow, you need:

- An n8n instance.
- Google Gemini API access.
- A Supabase project configured for vector storage.
- An accessible source website.
- Extraction rules that match the target website's structure.

Configure credentials within n8n. The Supabase vector configuration must match the output dimensions of the selected embedding model.

## Configuration and Testing

1. Set the source URL and target product pages.
2. Adjust HTML selectors and JavaScript transformations for the website.
3. Connect Google Gemini and Supabase credentials.
4. Configure the destination vector table and required database functions.
5. Test with a small sample of product pages.
6. Verify the extracted text, metadata, and stored embeddings.
7. Configure the schedule after validating the results.

## Scope and Limitations

- This project focuses on data collection and knowledge base preparation.
- A customer-facing chatbot or chat interface is not included.
- Extraction rules may need updates when the source website changes.
- Login-protected or dynamically rendered pages may require a different collection method.
- Scheduled execution alone does not prevent duplicate records. Configure and test record matching and update logic before recurring use.
- Hosting, API usage, and database costs depend on your own accounts and usage.

## Credential Safety

Never commit API keys, access tokens, passwords, or private customer data. Review workflow exports and screenshots before publishing them.

Only collect and use website content you are authorized to access.

## Author

**Haroon AI Automation**

Building practical n8n workflows, AI integrations, and business automations.
## Demo Video

[Watch the Product Scraper & RAG Automation Demo](./Product-Scraper-RAG-With-Voice.mp4)

## Project Status

Completed portfolio demo demonstrating product data extraction, content processing, Google Gemini embedding generation, and storage in Supabase.
