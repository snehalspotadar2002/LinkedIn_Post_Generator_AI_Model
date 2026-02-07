🚀 AI LinkedIn Post Generator (n8n Workflow)

An automated AI-powered LinkedIn content generation and publishing system built using n8n, OpenRouter (GPT/Gemini models), Google Sheets, and LinkedIn API.

This workflow automatically generates high-quality LinkedIn posts from structured inputs in Google Sheets and publishes them directly to LinkedIn after quality validation.

📌 Features

⏰ Scheduled automatic posting (daily at 9 PM)

📊 Reads post ideas from Google Sheets

🤖 AI-generated LinkedIn posts (150–300 words)

🧠 Structured JSON output parsing

🏷 Auto hashtag generation (3–5 hashtags)

📏 Character and quality validation

✅ Automatic quality check before publishing

🔄 Status tracking inside Google Sheets

🔗 Direct posting to LinkedIn profile

🏗 Workflow Architecture
1️⃣ Schedule Trigger

Runs daily at 21:00 (9 PM)

2️⃣ Google Sheets – Get Row

Fetches content ideas from Sheet

Pulls fields like:

Topic / Subject

Content Type

Tone

Target Audience

Additional Notes

3️⃣ Limit Node

Limits execution to one post per run

4️⃣ Update Status (In Progress)

Marks selected row as In Progress

5️⃣ AI Agent (LangChain Agent)

Generates LinkedIn post using:

GPT-3.5 (OpenRouter)

Gemini 2.0 Flash (fallback / structured formatting)

Enforces:

Hook in first line

Short paragraphs

3–5 hashtags

Call to action

JSON structured output

6️⃣ Structured Output Parser

Validates JSON format

Auto-fixes formatting issues

7️⃣ Post Formatter (Code Node)

Processes:

Combines post + hashtags

Counts characters

Counts words

Validates:

≤ 3000 characters

Minimum 3 hashtags

Adds metadata

Generates warnings if needed

8️⃣ Quality Validation (IF Node)

If quality passes → Publish

If fails → Regenerate

9️⃣ LinkedIn Node

Publishes post directly to LinkedIn profile

🔟 Update Google Sheet (Posted)

Updates row status to Posted

📂 Google Sheets Structure

Your Sheet must contain columns like:

Topic/Subject	Content Type	Tone	Target Audience	Additional Notes	Status	row_number

Status Flow:

Blank → In Progress → Posted

🤖 AI Output Format

The AI returns structured JSON:

{
  "post_content": "Full LinkedIn post text...",
  "hashtags": ["#AI", "#Marketing", "#Leadership"],
  "character_count": 285,
  "engagement_tip": "Best time to post: Tuesday-Thursday, 8-10 AM",
  "call_to_action": "Share your thoughts in comments!",
  "image_query": "AI, professional, office"
}

🛠 Requirements

n8n (Cloud or Self-hosted)

Google Sheets OAuth2 credentials

LinkedIn OAuth2 credentials

OpenRouter API key

Active LinkedIn profile

## 🖼️ Workflow Image
<img width="1402" height="591" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/2e2d56b8-7334-4030-8b11-28bd146fe478" />
