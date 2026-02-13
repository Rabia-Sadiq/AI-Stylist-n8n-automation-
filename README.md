
---

# 👗 AI-Powered Virtual Fashion Stylist

An end-to-end AI automation system that transforms a physical wardrobe into a structured, intelligent, and interactive digital styling assistant.

This project automatically analyzes clothing images, stores structured metadata, understands natural language outfit requests, selects appropriate outfits strictly from the user’s wardrobe, and generates a styled mannequin illustration.

---

## 🚀 Overview

This system solves three problems:

1. Digitizing a wardrobe automatically
2. Understanding natural language outfit requests
3. Generating realistic outfit visualizations

It combines automation, computer vision, NLP, database filtering, and image generation into one orchestrated workflow.

---

## ✨ Features

### 🧥 1. Smart Wardrobe Ingestion

* Watches a specific Google Drive folder
* Automatically detects newly uploaded clothing images
* Uses AI vision model to extract:

  * Type
  * Color
  * Formality
  * Season
  * Occasion Type
* Stores structured clothing data in Supabase

---

### 💬 2. Natural Language Outfit Requests

Users can send messages like:

* “I’m going to a cafe today”
* “Suggest something casual”
* “What should I wear to a wedding?”

The system:

* Extracts structured attributes from user intent
* Infers missing details intelligently
* Returns clean JSON
* Filters wardrobe accordingly

---

### 🧠 3. Intelligent Wardrobe Filtering

* Fetches wardrobe from Supabase
* Matches items based on:

  * Type
  * Color
  * Formality
  * Season
  * Occasion
* Supports partial and flexible matching
* Gracefully falls back if no exact match is found

---

### 👗 4. Strict AI Stylist Mode

The stylist model operates under strict constraints:

* Can ONLY select items already present in the wardrobe
* Cannot invent new clothing items
* Cannot modify attributes
* Must copy items exactly from database

This prevents hallucination and ensures realistic styling.

---

### 🎨 5. AI Outfit Illustration

* Selected clothing items are downloaded
* Sent to image editing model
* Generates a realistic full-body mannequin illustration
* Maintains accurate colors and textures
* No new accessories or items added

---

## 🏗 System Architecture

Image Upload
→ Google Drive Trigger
→ AI Vision Analysis
→ JSON Parsing
→ Store in Supabase

User Message
→ Intent Extraction
→ Wardrobe Fetch
→ Filtering Logic
→ Strict AI Stylist
→ Extract Image Links
→ Generate Styled Illustration

---

## 🛠 Tech Stack

* n8n (Workflow Automation Engine)
* Google Drive (Wardrobe Storage)
* Google Gemini (Image Analysis)
* OpenAI (Intent Extraction + Styling + Image Editing)
* Supabase (Database)

---

## 📂 Database Schema (Supabase: `wardrobe` Table)

| Field           | Description                    |
| --------------- | ------------------------------ |
| type            | Clothing type                  |
| color           | Clothing color                 |
| formality       | Casual / Formal / Smart Casual |
| season          | Suitable season                |
| occasion_type   | Usage context                  |
| drive_file_id   | Google Drive file ID           |
| drive_file_link | Direct file link               |
| email           | User identifier                |
| created_at      | Timestamp                      |

---

## 🧩 Design Principles

* Multi-model AI orchestration
* Anti-hallucination prompt constraints
* JSON-only AI responses
* Modular automation workflow
* Scalable database filtering logic

---

## 🎯 Use Case

This system simulates a real-world AI stylist that:

* Digitizes a physical wardrobe
* Understands human language
* Makes context-aware outfit decisions
* Generates visual outfit presentations

---

## 📌 Current Status

* Fully functional end-to-end workflow
* Automated wardrobe ingestion
* AI-based outfit selection
* AI-generated mannequin visualization


## 👩‍💻 Author

@Rabia-Sadiq
---

