# SpendSense AI – Simple Personal Finance Tracker

SpendSense AI is a privacy-friendly, AI-powered app to help you instantly organize and understand your personal spending. Just paste your bank SMS, email summaries, or statement text, and let SpendSense AI do the rest!

---

## 🚀 What SpendSense AI Does

- **Parses** your bank messages or statement text (no need to upload files to a server).
- **Categorizes** expenses (e.g., Food, Utilities, Travel).
- **Summarizes** your spending in a clear table, text, or JSON.
- **Answers questions** like “How much did I spend on shopping last month?” using natural language.
- **Suggests reminders** for upcoming bills and recurring payments (optional).

---

## 🧠 Generative AI Features Covered

- **System & User Prompts**:  
  The AI is instructed with clear roles (e.g., “You are a finance tracker assistant”), while users input free-form queries.

- **Tuning Parameters**:  
  Choose summary type (table, JSON, text) and filter by time period (all, month, week).

- **Structured Output**:  
  Expenses are displayed as tables or JSON so you can easily copy, visualize, or export.

- **Function Calling**:  
  AI calls small functions to parse text, create summaries, or generate reminders.

- **RAG (Retrieval-Augmented Generation)**:  
  The AI fetches answers from your real data—so responses are always personalized and accurate.

---

## 💻 Tech Stack & Tools

- **Python** for main logic and AI integration
- **Streamlit** for the simple web interface (easy to run with one command)
- **OpenAI, Claude, or HuggingFace** for natural language processing and AI responses
- **Regex** for parsing SMS/text statements
- Optional: **pdfplumber** for PDF import, **pandas** for dataframes/tables

---

## ✨ How to Use

1. **Run the app:**  

2. **Paste your expense SMS, email, or statement text** into the app.

3. **Choose how you want the summary:** table, JSON, or text.

4. **Ask expense questions in plain English** (example: “Show my food spending for August”).

5. **Get instant, structured insights**—download, export, or just copy as needed.

---

## 🎯 Why SpendSense AI?

- **No account required** – works locally for privacy
- **Fast and simple UI** – all analysis is instant
- **GenAI under the hood** – real NLP, structured data, smart prompts

---

## 🧩 Example

**Input:**  
> SMS: “Your account was debited ₹2,000 for Zomato. Electricity bill ₹1,200 paid.”

**Output:**

| Category   | Amount  |
|------------|---------|
| Food       | ₹2,000  |
| Utilities  | ₹1,200  |

**Ask:**  
> “How much did I spend on food?”
**AI:**  
> “You spent ₹2,000 on Food.”

---

## 📞 Questions?

Feel free to open an issue or suggest new features (like bill reminder notifications!).

---
