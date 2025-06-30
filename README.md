# 🧾 GLR Report Generator with Streamlit + LLM

This Streamlit app automates General Loss Report (GLR) generation for insurance templates such as USAA, Wayne, and GuideOne. It extracts information from a photo report PDF and populates a .docx template using an OpenRouter LLM.

🎯 Goal: Generate a filled GLR .docx document using text extracted from image-based reports.

---

## 📁 Folder Structure

<pre>
task3-glr-report-generator/
├── task_3_code.py                  # Main Streamlit app
├── .streamlit/secrets.toml.example# Example secret config (no real key)
├── templates/                      # Example GLR templates (.docx)
├── sample-reports/                # Example input photo reports (.pdf)
├── generated-output/              # Output filled-in GLR reports (.docx)
├── screenshots/                   # Streamlit app screenshots
└── README.md                      # This file
</pre>

---

## 🌐 Sample Interface

![Streamlit Screenshot](screenshots/glr_ui.png)

---

## 🚀 Features

- 📂 Upload photo report (PDF)
- 📄 Upload insurance template (DOCX)
- 🤖 LLM auto-extracts fields from photo report
- 📝 Final .docx is generated and downloadable

---

## 🧠 Supported Templates

| Provider      | Format Identifier     |
|---------------|------------------------|
| USAA          | [INSURED_NAME], ...    |
| Wayne/Elevate | [XM8_INSURED_NAME], ...|
| GuideOne/Eberl| [XM8_INSURED_...], GUIDEONE mentioned |

Detection is automatic.

---

## ▶️ How to Run

1. Install requirements: pip install streamlit python-docx PyMuPDF requests
2. Create a secrets file: 📄 .streamlit/secrets.toml
   [OPENROUTER_API_KEY = "your-api-key-here"]
3. Run the app: streamlit run task_3_code.py
4. Upload your photo report PDF and matching GLR template DOCX.
The filled report will be generated and downloadable!

## 🧪 Example Workflow
Upload	Output
photo-report.pdf	Completed GLR Word Doc.docx
USAA_Template.docx	(auto-filled using LLM)

## 💬 Notes
Supports OpenRouter API (free models like mistral-7b-instruct)

Each template must have placeholders in [FIELD] format

All text from PDF is parsed using PyMuPDF

## 🧰 Example Models
You can update task_3_code.py to switch to another model from OpenRouter. Default is:

model = "mistralai/mistral-7b-instruct"
Other options include:

openchat/openchat-3.5

cohesion/command-r

google/gemma-7b

## 📬 Contact
GitHub: basi1l
