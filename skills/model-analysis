---
name: HuggingFace Model Trends Analysis
description: Teaches how to analyze model data from the Hugging Face Hub API to explore trends, compare models, and draw insights from the open-source AI ecosystem.
---

# HuggingFace Model Trends Analysis

## Overview

This skill teaches you how to analyze model data from the Hugging Face Hub API.
The Hugging Face Hub is the largest open-source AI model repository in the world,
hosting over 1 million public models across a wide range of tasks, organizations,
and frameworks. Use this skill to help users explore trends, compare models,
and draw insights from the ecosystem.

---

## Data Source

All model data is fetched from the Hugging Face Hub public API:
`https://huggingface.co/api/models`

No authentication is required. The API returns a list of model objects.

---

## Understanding the Data Fields

| Field | Description |
|---|---|
| `id` | The model identifier in the format `organization/model-name`. |
| `likes` | Number of times the model has been liked by the community. A proxy for community engagement and reputation. |
| `downloads` | Number of times the model has been downloaded. A proxy for real-world usage and adoption. |
| `pipeline_tag` | The primary task the model is designed for (e.g. `text-generation`, `image-classification`, `sentence-similarity`). Use this to group and compare models by task type. |
| `library_name` | The ML framework the model is built with (e.g. `transformers`, `timm`, `sentence-transformers`, `diffusers`). |
| `tags` | A list of metadata tags including license type, datasets used, arXiv papers, deployment regions, and more. |
| `private` | Whether the model is publicly available (`false`) or gated/private (`true`). |
| `createdAt` | The date the model was published to the Hub. Use this for trend analysis over time. |
| `modelId` | Duplicate of `id`. Can be ignored. |

---

## Key Concepts

### Downloads vs. Likes

Downloads reflect how often a model is actually used in production or research.
Likes reflect community appreciation and visibility. These two metrics do not
always correlate — a highly downloaded model may have few likes if it is used
programmatically rather than discovered through the Hub UI, and vice versa.

### Organizations

The first part of the `id` field (before the `/`) is the organization or user
that published the model. Examples include `meta-llama`, `google`, `openai`,
`microsoft`, `BAAI`, and `sentence-transformers`. Use this to analyze which
organizations dominate the ecosystem.

### Pipeline Tags

Common pipeline tags include:

- `text-generation` — large language models for chat, completion, and reasoning
- `text-classification` — sentiment analysis, topic classification
- `token-classification` — named entity recognition, POS tagging
- `image-classification` — vision models
- `sentence-similarity` — embedding models for semantic search and RAG
- `automatic-speech-recognition` — speech to text
- `text-to-image` — image generation models
- `fill-mask` — masked language models like BERT and RoBERTa
- `zero-shot-image-classification` — vision-language models like CLIP

### Licenses

License information is embedded in the `tags` field with the prefix `license:`.
Common licenses include `apache-2.0`, `mit`, `llama3`, `gemma`, and `cc-by-4.0`.
License type matters for commercial use — Apache 2.0 and MIT are the most permissive.

---

## How to Use This Skill

**When the user asks a general question about the ecosystem:**
Fetch the full model list and analyze across multiple dimensions —
task types, organizations, downloads, likes, and licenses.

**When the user asks about a specific model or organization:**
Filter the fetched data by the `id` field to find relevant models.

**When the user asks about trends:**
Use the `createdAt` field to group models by year or month and identify
growth patterns in specific task categories or organizations.

**When the user asks for a comparison:**
Use `downloads` and `likes` side by side. Note any divergence between
the two metrics and explain what it might mean.

---

## Example Prompts and How to Handle Them

**"What are the most popular models right now?"**
Sort by `downloads` descending. Return the top 25 with model name,
organization, task type, downloads, and likes.

**"Which organizations have the most influence on HuggingFace?"**
Extract the organization from the `id` field. Aggregate total downloads
and likes by organization. Return the top 10.

**"What types of models are people using the most?"**
Group by `pipeline_tag`. Sum downloads per tag. Return a ranked list
with download counts.

**"Is there a correlation between likes and downloads?"**
Pass the data to the analysis agent for a correlation analysis and
scatter plot visualization.

**"What are the most popular open-source licenses?"**
Extract license tags (prefix `license:`) from the `tags` field.
Count occurrences and return a ranked breakdown.

---

## Analysis Best Practices

- Always clarify whether the user wants analysis by downloads, likes, or both.
- When presenting model names, always include the organization prefix for clarity.
- When summarizing large datasets, lead with the most surprising or interesting finding.
- If the user asks a question that requires visualization, delegate to the analysis agent.
- Always note the limitations of the data — downloads are cumulative, so older models
  naturally have higher counts than newer ones.
