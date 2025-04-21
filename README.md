```markdown
# 🩻 Chest X-ray Report Generator using Clinical-T5 and RAD-DINO

A fully functional, medically formatted PDF report generator for chest X-rays. Built using Streamlit, this system combines image embeddings from **RAD-DINO** with a **fine-tuned Clinical-T5** model to generate clean, structured radiology findings. It includes a professional letterhead, clinic logo, digital signature, and stores logs of all reports.

---

## 🧠 Key Features

- 📤 Upload chest X-ray images (`.jpg`, `.png`)
- 🤖 Generate bullet-pointed **radiology findings** using RAD-DINO + Clinical-T5
- 📄 Auto-generate multi-page PDF reports with:
  - Clinic header
  - Patient details
  - Structured findings
  - Doctor signature & clinic logo
  - X-ray image on the second page
- 📊 Log every report to `report_logs.csv`
- 💬 Optional extension for:
  - Sending email with report
  - QR-code based report verification

---

## 🗂 Project Structure

```
chestxray_report_app/
├── app.py                        # Main Streamlit app
├── requirements.txt              # Python dependencies
├── README.md
├── .gitignore
├── models/
│   └── clinical_t5_final/        # Pretrained Clinical-T5 model
├── utils/
│   └── dino_embedding.py         # RAD-DINO feature extraction
├── assets/
│   ├── logo.png                  # Clinic logo
│   └── signature.png            # Doctor’s digital signature
└── outputs/
    ├── reports/                  # Generated PDFs & images
    └── report_logs.csv           # Logged metadata
```

---

## 🚀 Setup Instructions

### 📥 Clone the Repo

```bash
git clone https://github.com/yourusername/chestxray-report-generator.git
cd chestxray-report-generator
```

### 🛠️ Create Environment & Install Requirements

```bash
conda create -n cxr-report-gen python=3.10 -y
conda activate cxr-report-gen
pip install -r requirements.txt
```

---

## ▶️ Running the App

```bash
streamlit run app.py
```

App will launch at: `http://localhost:8501`

---

## 📄 Sample Output

- **PDF Includes**:
  - Patient metadata
  - Clean, grammatically formatted findings (auto-corrected)
  - X-ray image (page 2)
  - Header/footer with clinic info
  - Doctor's name & digital signature
- **CSV Log**:
  - Stored in `outputs/report_logs.csv`
  - Includes patient name, dates, report path

---

## 🧠 Model Info

- **Image Encoder**: [`StanfordAIMI/RAD-DINO`](https://huggingface.co/StanfordAIMI/RAD-DINO)
- **Text Generator**: Fine-tuned `Clinical-T5-Sci`
- **Prompt Engineering**: Uses semantic token prompts derived from image features

---

## 🔐 Customization

| Feature         | File              | Notes                                    |
|----------------|-------------------|------------------------------------------|
| Clinic Logo     | `assets/logo.png` | Displayed top-left of report              |
| Doctor Signature| `assets/signature.png` | Displayed bottom-right on all pages |
| T5 Model        | `models/clinical_t5_final/` | Replace with any fine-tuned model  |
| Report Format   | `create_letterhead_pdf()` in `app.py` | Modify layout or styles          |

---

## 🧱 Future Enhancements

- ✅ Email report directly via SMTP
- ✅ QR code on PDF for online verification
- 🧾 Impression section generation (next step)
- 📡 PACS/DICOM or FHIR integration

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 👨‍⚕️ Author

**Yash Verma**  
Clinical-AI & Multimodal Fusion Researcher  
_NLP_Project | 2025_

---

## 🤝 Contributions

Feel free to fork this repo and submit pull requests!  
Want help deploying or extending? Open an issue or reach out.
```
