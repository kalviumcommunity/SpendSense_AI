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

## 🧠 Zero-Shot Prompting

## 🔹 What is Zero-Shot Prompting?

**Zero-shot prompting** means giving an AI model (like GPT) a **task without providing any examples** beforehand.  
You only describe what you want in natural language, and the model uses its pretraining knowledge to respond correctly.  

👉 In short: **“Do this task, even though I haven’t shown you any examples.”**

---

## 🔹 Why "Zero-Shot"?

The name comes from ML terminology:

- **Few-shot learning** → Provide a few examples before asking the model to generalize.  
- **Zero-shot learning** → No examples, just instructions.

---

### 🔹 System Prompt  

You are an AI Code Reviewer. Your role is to analyze the given code, identify bugs, suggest improvements, and provide structured feedback. Always return results in a JSON format containing:  

- `issues`: List of detected bugs or problems  
- `suggestions`: Recommended improvements  
- `overall_feedback`: Summary of code quality  

### 🔹 User Prompt  

Review the following Python code and provide feedback as per the defined schema:  

```python
def add_numbers(a, b):
    return a - b  # intended to be addition
````

### 📌 RTFC Framework Usage

* **R (Role):** Defined in the system prompt as a code reviewer.
* **T (Task):** Analyze code, detect bugs, and suggest improvements.
* **F (Format):** Responses must follow a structured JSON output.
* **C (Context):** The provided code snippet and programming language.

### 🔹 One-Shot Prompt  

**System Prompt:**  
You are an AI code reviewer. Analyze the given code, detect bugs, and suggest improvements.  
Always return results in JSON format with three fields: `issues`, `suggestions`, and `overall_feedback`.  

**User Prompt (with one example):**  

Example Input (Python):  
```python
def divide(a, b):
    return a * b  # intended to be division
````

Example Expected Output (JSON):

```json
{
  "issues": ["The operator used is multiplication instead of division."],
  "suggestions": ["Replace '*' with '/' to correctly divide the numbers."],
  "overall_feedback": "Logic error detected in the function implementation."
}
```

Now review the following Java code:

```java
public int Subtract(int a, int b) {
    return a + b; // intended to be subtraction
}
```

### 📌 Why One-Shot Prompting?

* Provides **one guiding example** to set the response pattern.
* Ensures the AI generates **consistent, structured outputs**.
* Reduces ambiguity compared to zero-shot prompting.

## 🎯 Multi-Shot Prompting  

In CodeSage, we apply **Multi-Shot Prompting**, where the AI is provided with **multiple examples** before being asked to solve the real task.  
This method ensures the AI clearly understands the **pattern, structure, and expectations** of the output.  

### 🔹 Multi-Shot Prompt  

**System Prompt:**  
You are an AI code reviewer. Analyze the given code, detect bugs, and suggest improvements.  
Always return results in JSON format with three fields: `issues`, `suggestions`, and `overall_feedback`.  

**User Prompt (with multiple examples):**  

Example 1 (Python):  
```python
def add(a, b):
    return a - b  # intended to be addition
````

Expected Output:

```json
{
  "issues": ["The operator used is subtraction instead of addition."],
  "suggestions": ["Replace '-' with '+' to correctly add the numbers."],
  "overall_feedback": "Logic error detected in the addition function."
}
```

Example 2 (JavaScript):

```javascript
function square(n) {
    return n + n; // intended to be square
}
```

Expected Output:

```json
{
  "issues": ["The function doubles the number instead of squaring it."],
  "suggestions": ["Replace 'n + n' with 'n * n' to correctly square the number."],
  "overall_feedback": "Incorrect mathematical operation for squaring."
}
```

Now review the following C++ code:

```cpp
int multiply(int a, int b) {
    return a - b; // intended to be multiplication
}
```

### 📌 Why Multi-Shot Prompting?

* Gives the AI **multiple reference patterns** to ensure consistent results.
* Helps in **complex tasks** where one example isn’t enough.
* Reduces errors and improves **accuracy of code reviews**.

## 🎯 Dynamic Prompting  

In CodeSage, we use **Dynamic Prompting**, where the prompt is automatically adapted based on the **user’s input context** (e.g., programming language, code style, or desired output format).  
This makes the system **flexible and personalized**, instead of relying on fixed instructions.  

### 🔹 Dynamic Prompt Example  

**System Prompt (Template):**  
You are an AI code reviewer. Analyze the given code in **{{language}}**, detect bugs, and suggest improvements.  
Always return results in JSON format with three fields: `issues`, `suggestions`, and `overall_feedback`.  

**User Prompt (Generated Dynamically):**  
Review the following **{{language}}** code:  

```{{language}}
{{code_snippet}}
````

### Example Execution

If the user provides **Python code**:

```python
def divide(a, b):
    return a * b  # intended to be division
```

The dynamically generated prompt becomes:

```text
You are an AI code reviewer. Analyze the given code in Python, detect bugs, and suggest improvements.
Always return results in JSON format with three fields: issues, suggestions, and overall_feedback.

Review the following Python code:
def divide(a, b):
    return a * b  # intended to be division
```

Expected Output:

```json
{
  "issues": ["The function multiplies instead of dividing."],
  "suggestions": ["Replace '*' with '/' to correctly perform division."],
  "overall_feedback": "Incorrect operator used for division."
}
```

### 📌 Why Dynamic Prompting?

* Automatically adapts prompts to **any programming language**.
* Makes the system more **scalable and user-specific**.
* Reduces manual work while ensuring **consistent structured outputs**.