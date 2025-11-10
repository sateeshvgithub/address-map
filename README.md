# address-map
simplefied address mapping tool that can be embedded  ur react portal

Here’s a **ready-to-publish `README.md`** for your GitHub challenge repo 👇

---

```markdown
# 🧩 Challenge: Free-Form Indian Address Parser (React / JavaScript)

## 🎯 Objective
Your challenge is to build a **React or JavaScript web app** that takes **free-form Indian address text** and intelligently extracts structured fields such as:

- First & Last Name  
- Phone Number  
- Pin Code  
- State  
- City  
- Landmark  
- C/O (Care Of)  
- Unmapped Text  
- Truncation Notice / Error Messages  

The goal is to simulate how a logistics or e-commerce system might normalize unstructured address text into database-friendly fields.

---

## 🧱 Requirements

### 1️⃣ Input
- Provide a single **text area** where users can paste or type an address (multi-line or comma-separated).
- Example inputs:
```

Mr Ramesh Kumar, Brundavanam colony dno 11111, Near Ram temple, Chennai 600001, Phone: +91 9876543210

```
```

Smt. Lakshmi, Flat 12, Sai Enclave, Banjara Hills, Hyderabad 500034, 9840123456

```

### 2️⃣ Parsing Logic
From the input text, extract or infer the following fields:

| Field | Description |
|-------|--------------|
| **First Name** | From name tokens (e.g., Mr Ramesh Kumar → Ramesh) |
| **Last Name** | Remaining part of the name |
| **Phone Number** | Detect 10-digit Indian numbers (+91 optional) |
| **Pin Code** | 6-digit number |
| **State** | Must match any of the 36 Indian states/UTs |
| **City** | Detect from a known set of major Indian cities |
| **Landmark** | Lines containing words like *near*, *opp*, *beside*, *lane*, *colony*, etc. |
| **C/O** | Text starting with “C/O”, “c/o”, or “care of” |
| **Unmapped Text** | Any leftover parts not mapped to fields |
| **Truncation Notice** | If input exceeds a threshold (default 256 chars) |
| **Errors** | e.g., “Phone missing”, “Too many characters”, “Name not found” |

---

## ⚙️ Behavior Rules

- If input length > **500 characters**, display **error**: `too_many_characters`.
- If input length > **256 characters**, mark as **truncated** but still parse.
- Display results in a neat table or list.
- Highlight **missing** or **error** fields clearly (e.g., red text).
- No backend — everything must be handled **client-side**.

---

## 💻 Frontend UI Requirements

- Use **React** (preferred) or plain **JavaScript + HTML + CSS**.
- UI must include:
- Text area for input  
- “Parse” button  
- “Clear” button  
- Output section showing all fields and errors  
- Optional “Try Sample” buttons for quick testing  

Example layout:
```

[ Text Area for Address ]
[ Parse ] [ Clear ]

Parsed Result:
First Name: Ramesh
Last Name: Kumar
Phone: 9876543210
City: Chennai
Pincode: 600001
...

````

---

## 🧪 Test Coverage

- Write **20 automated test cases** (using Jest or Vitest).  
- Each test should verify:
  - Input → Expected structured output
  - Edge cases like missing phone, too long text, unknown city/state, etc.

### Example Test Case
```js
test('Parses simple Chennai address', () => {
  const result = parseAddress(
    'Mr Ramesh Kumar, Brundavanam colony, Near Ram temple, Chennai 600001, Phone: 9876543210'
  );
  expect(result.city).toBe('Chennai');
  expect(result.pincode).toBe('600001');
  expect(result.phone).toBe('9876543210');
  expect(result.errors.length).toBe(0);
});
````

---

## 🚀 Getting Started

### 1️⃣ Clone the repo

```bash
git clone https://github.com/<your-username>/indian-address-parser-react.git
cd indian-address-parser-react
```

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Run the app locally

```bash
npm run dev
```

Then open your browser at:
👉 **[http://localhost:5173](http://localhost:5173)**

### 4️⃣ Run tests

```bash
npm test
```

---

## 🧰 Technical Requirements

* Must use **React + Vite** (preferred) or **Create React App**.
* Include the following in your repo:

  * `package.json` with scripts (`dev`, `build`, `test`)
  * `src/` folder with parsing logic in a separate utility file
  * `__tests__/` folder for automated tests
  * `README.md` (this file)
* Should be deployable on **GitHub Pages**, **Vercel**, or **Netlify**.

---

## 💡 Hints & Ideas

* You may use **regex** for parsing phone/pincode/state/city.
* Maintain a **list of known Indian states and major cities**.
* Normalize text before processing (trim, remove commas/newlines).
* For unmapped fields, display the leftover cleaned string.
* Use `toLowerCase()` comparisons for robust detection.

---

## 🏆 Bonus Challenges

* Handle multilingual inputs (Hindi + English mix)
* Validate pincode ranges against real India Post data
* Add an “auto-format to JSON” button
* Suggest corrections for misspelled city/state names

---

## 🧾 Sample Output

**Input:**

```
Mr Ramesh Kumar, Brundavanam colony dno 11111, Near Ram temple, Chennai 600001, Phone: +91 9876543210
```

**Output:**

| Field      | Value                        |
| ---------- | ---------------------------- |
| First Name | Ramesh                       |
| Last Name  | Kumar                        |
| Phone      | 9876543210                   |
| Pincode    | 600001                       |
| State      | Tamil Nadu                   |
| City       | Chennai                      |
| Landmark   | Near Ram temple              |
| C/O        | —                            |
| Unmapped   | Brundavanam colony dno 11111 |
| Truncated  | No                           |
| Errors     | None                         |

---

## 📦 Deliverables

1. Public **GitHub repository** containing:

   * Source code
   * Test suite
   * `README.md` with instructions
   * Deployment link (if hosted)
2. At least **20 working automated test cases**
3. Code must be **linted**, **readable**, and **self-contained**

---

## 🧠 Evaluation Criteria

| Category               | Weight | Description                                             |
| ---------------------- | ------ | ------------------------------------------------------- |
| **Parsing Accuracy**   | 40%    | Correctness of extracted fields                         |
| **Code Quality**       | 20%    | Readability, structure, modularity                      |
| **UI/UX**              | 20%    | Clarity, usability, error visibility                    |
| **Testing & Coverage** | 10%    | Automated test completeness                             |
| **Bonus Features**     | 10%    | Creative improvements (e.g., suggestions, localization) |

---

**Good luck, and have fun parsing the chaos of Indian addresses! 🇮🇳**

```
---

Would you like me to add a **grading rubric (0–5 scale per category)** to this README for use in hackathon or evaluation?
```
