
# 🧩 Challenge 2 — Aadhaar Processing Webpage

### 🎯 Objective

Develop a **webpage (HTML + JavaScript)** that accepts an **Aadhaar file** (either a PDF or an image) and provides **two operations** based on user choice.

---

## 💻 Task Description

Your webpage should allow a user to **upload** an Aadhaar document (PDF or image).
Once uploaded, the user should select one of the following **choices**:

### **Choice 1: Create a Masked Aadhaar**

* Detect the Aadhaar number from the uploaded file.

* Mask the first 8 or 12 digits of the Aadhaar number.

* Only the **last 4 digits** should remain visible.
  Example:

  ```
  Real Aadhaar: 1234 5678 9123 4567
  Masked Aadhaar: XXXX XXXX XXXX 4567
  ```

* The output should display or download the masked version of the Aadhaar (text or image).

---

### **Choice 2: Extract Aadhaar Details**

Extract and display the following fields from the uploaded document:

1. Aadhaar Number
2. Name
3. Address
4. Phone Number (if available)

The extracted values should be shown clearly on the webpage.

---

## 🧠 Hints

* Use any **JavaScript OCR library** (like `Tesseract.js`) to read text from images or PDFs.
* Handle **both PDF and image** file types.
* Implement **basic validations** (e.g., file type, file size < 5 MB).
* Keep the UI simple — file upload box, radio buttons for choice, and output area.

---

## ✅ Test Cases

| **Test Case** | **Input File Type**             | **Expected Behavior**         | **Expected Output**                                                                                                       |
| ------------- | ------------------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| TC1           | Aadhaar Image (JPG)             | User selects “Mask Aadhaar”   | Output shows masked number like `XXXX XXXX XXXX 6789`                                                                     |
| TC2           | Aadhaar PDF                     | User selects “Extract Fields” | Fields extracted correctly: Aadhaar: `XXXX XXXX XXXX 1234`, Name: `Ravi Kumar`, Address: `Hyderabad`, Phone: `9876543210` |
| TC3           | Non-Aadhaar image (random text) | User selects “Extract Fields” | Show error message “Aadhaar number not found”                                                                             |
| TC4           | PDF > 5MB                       | Any option                    | Display validation error “File too large. Please upload a smaller file.”                                                  |
| TC5           | Blank upload                    | User clicks “Process”         | Show validation error “Please upload a file.”                                                                             |

---

## 📦 Deliverables

* A single **HTML file** (or JHTML if your environment supports it).
* Containing inline **JavaScript** and **CSS**.
* No backend processing — all logic should run **in-browser**.

---

## 🏁 Bonus Points

* Support **drag-and-drop** upload.
* Provide a **preview** of the masked Aadhaar.
* Use async processing to handle large PDFs efficiently.

