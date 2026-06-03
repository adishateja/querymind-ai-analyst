# querymind-ai-analyst
AI-powered data analyst — upload any CSV and ask questions in plain English
readme = """# 🧠 QueryMind — AI Data Analyst

An AI-powered data analysis tool where non-technical users can upload any dataset and ask questions in plain English — no coding required.

## 🎯 Live Demo
👉 [Try it here](https://776a92702f55a7873b.gradio.live )

## 🚀 What it does
- Upload any CSV, Excel, or JSON file
- Ask questions in plain English
- AI generates Python/Pandas code automatically
- Results shown instantly as tables or text

## 🏗️ Architecture
User uploads file → Schema extracted (not full data)
↓
Gemini 2.5 Flash receives schema + question
↓
LLM generates Python/Pandas code
↓
Sandboxed environment executes code safely
↓
Self-correction loop handles any errors
↓
Result returned to user
## 🔒 Key Technical Decisions

### 1. Schema extraction, not full data
Only column names, data types and 3 sample rows are sent to the LLM — not the full dataset. This protects data privacy and reduces API costs.

### 2. Sandboxed execution
LLM-generated code runs in a restricted environment with `__builtins__` stripped. Only pandas and numpy are injected. This blocks file system access, shell commands and network requests from untrusted code.

### 3. Self-correction retry loop
If generated code fails, the error message is fed back to the LLM with the original question. The model fixes its own mistake. Max 3 attempts before returning a clean failure message.

### 4. Temperature = 0
Deterministic output for code generation — same question always produces the same code. No randomness when correctness matters.

## 🛠️ Tech Stack
| Layer | Technology |
|---|---|
| LLM | Google Gemini 2.5 Flash |
| Data processing | Python, Pandas |
| UI | Gradio |
| Execution | Sandboxed Python exec() |

## ⚙️ Run it yourself

1. Clone this repo
2. Install dependencies: `pip install pandas openpyxl gradio google-genai`
3. Get a free Gemini API key from https://aistudio.google.com/app/apikey
4. Replace `YOUR_KEY_HERE` in the code
5. Run the notebook in Google Colab

## 📁 Supported File Types
- CSV (.csv)
- Excel (.xlsx, .xls)
- JSON (.json)

## 🧠 Example Questions
- "What is the total revenue per product?"
- "Which region had the highest sales?"
- "Show me the top 3 performing products"
- "What is the average order quantity?"

## 👤 Author
Built as a portfolio project demonstrating LLM integration, prompt engineering, and safe code execution patterns.
"""




