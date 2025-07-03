
# ✈️ Trippy - Conversational Travel AI Agent 

This project is an **AI-powered travel assistant** built using [n8n](https://n8n.io). It takes in a user’s travel request, extracts relevant information using LLMs, gathers real-time data (activities, resorts, flights), and emails back a personalized travel plan — all in one seamless flow.

---

## 🧠 Features

- **Conversational AI Interface** via Webhook
- **LLM Parsing** (OpenAI GPT-4o & Claude 3.5) for:
  - Extracting travel dates and locations
  - Generating email content
- **Third-party APIs** to fetch:
  - Things to do (Activities)
  - Resorts
  - Flights
- **Automated Plan Delivery** via Gmail
- **End-to-end Flow** from webhook to response

---

## 🔧 Workflow Breakdown

```text
Webhook
   ↓
Set Fields (manual defaults/input shaping)
   ↓
AI: Airport Codes & Dates (LLM + Parser)
   ↓
API: Activities (Tavily)
   ↓
API: Resorts (SerpAPI)
   ↓
API: Flights (SerpAPI)
   ↓
AI Agent: Email Generation (Claude 3.5 + Parser)
   ↓
Send Plan via Gmail
   ↓
Respond to Webhook
````

---

## 🔌 Integrations Used

* **OpenAI GPT-4o**
* **Anthropic Claude 3.5**
* **Tavily API** – for activity recommendations
* **SerpAPI** – for resort & flight search
* **Gmail API** – for email delivery
* **Custom Webhook** – entry point

---

## 📦 Setup Instructions

1. **Clone the repo** or upload the `travel-ai-workflow.json` file to your n8n instance.
2. Configure credentials for:

   * OpenAI
   * Claude (Anthropic)
   * SerpAPI
   * Tavily
   * Gmail
3. Adjust prompts, filters, and mappings as needed.
4. Deploy the webhook and test using a tool like Postman or a chatbot frontend.

---

## 📝 Example Input

```json
{
  "message": "I want to go to Bali next month with my family. Can you help me plan?"
}
```

---

## 📧 Output

The user receives a rich, AI-generated email with:

* Flight options
* Resorts to stay at
* Activities to do
* Trip summary (personalized)

---

## 📁 Files

* `travel-ai-workflow.json` – Main workflow
* `README.md` – This file

---

## 🛠️ To-Do

* [ ] Add validation for missing fields
* [ ] Improve multi-turn context memory
* [ ] Create a frontend chatbot wrapper

---

## 📍 License

MIT – Feel free to use, remix, or contribute.

---

## 🙌 Credits

Built with ❤️ using [n8n](https://n8n.io), OpenAI, Claude, and the power of automation.

```
