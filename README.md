👗 AI-Powered Virtual Fashion Stylist (n8n Automation)

An end-to-end AI-powered wardrobe management and outfit generation system built using automation, computer vision, NLP, and image generation.

This system allows users to upload clothing items, automatically analyzes them using AI, stores structured metadata, understands natural language outfit requests, selects appropriate outfits strictly from the user’s wardrobe, and generates a styled mannequin illustration.

🚀 Features
1️⃣ Smart Wardrobe Ingestion

Watches a specific Google Drive folder

Automatically detects newly uploaded clothing images

Uses AI vision model to extract:

Type

Color

Formality

Season

Occasion type

Stores structured data in Supabase

2️⃣ Natural Language Outfit Requests

Users can send messages like:

“I’m going to a cafe today”

“I need something casual”

“Suggest an outfit for a wedding”

The system:

Extracts structured attributes from user intent

Infers missing details intelligently

Returns clean JSON

3️⃣ Intelligent Wardrobe Filtering

Fetches wardrobe from Supabase

Filters based on:

Type

Color

Formality

Season

Occasion

Supports partial matching

Falls back gracefully if no exact match is found

4️⃣ Strict AI Stylist Mode

The stylist model:

Can ONLY select items already in the wardrobe

Cannot invent new clothing

Cannot modify colors or attributes

Must copy items exactly from database

This prevents hallucination and ensures realistic styling.

5️⃣ AI Outfit Illustration

Selected outfit items are downloaded

Sent to image editing model

Generates a realistic mannequin illustration

Maintains exact colors and clothing details

No extra accessories added

🏗 Architecture Overview

Upload Image
→ Google Drive Trigger
→ Vision AI Analysis
→ JSON Cleanup
→ Store in Supabase

User Chat
→ Intent Extraction
→ Filter Wardrobe
→ Strict AI Stylist
→ Extract Drive Links
→ Generate Styled Illustration

🛠 Tech Stack

n8n (Workflow Automation)

Google Drive (Wardrobe Storage)

Google Gemini (Image Analysis)

OpenAI (Intent Extraction + Styling + Image Editing)

Supabase (Database)

🧠 Key Design Principles

Multi-model orchestration

Strict anti-hallucination constraints

JSON-only AI outputs

Graceful fallback filtering logic

Automation-first architecture

Modular node-based design

📂 Database Structure (Supabase Table: wardrobe)
Field	Description
type	Clothing type
color	Clothing color
formality	Casual / Formal / etc
season	Season suitability
occasion_type	Usage context
drive_file_id	Google Drive file ID
drive_file_link	Direct link
email	User identifier
created_at	Timestamp
🎯 Use Case

This system simulates a real-world AI stylist that:

Digitizes a user’s physical wardrobe

Understands human language

Makes context-aware outfit decisions

Visually presents styled outfits

📌 Current Status

Fully functional end-to-end workflow

Supports automated wardrobe ingestion

Supports AI-based outfit generation

Generates styled mannequin illustrations

Future improvements may include:

Multi-user authentication

Weather-based recommendations

Mood-based styling

Outfit history memory

Frontend UI integration
