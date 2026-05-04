# Assignment 1 – Transliteration Accuracy Testing
**IT3040 – ITPM | BSc (Hons) in Information Technology | Year 3 | Semester 1**

This project tests the **Chat Sinhala transliteration** accuracy of [pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator) using Playwright automation.

---

## Project Structure

```
├── test_automation.py              # Main Playwright automation script
├── README.md                       # This file
└── Assignment 1 - Test cases.xlsx  # Test cases with results
```

---

## Prerequisites

- Python **3.11** or **3.12**
- Google Chrome (recommended) or Playwright will install Chromium automatically

---

## Installation (One-Time Setup)

### 1. Clone the repository

```bash
git clone <https://github.com/Malmi9306/IT3040-Assignment-1-Transliteration-Testing>
cd test_automation
```

### 2. Install dependencies

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## How to Run the Tests

### Step 1 – Prepare the Excel file

Open `Assignment 1 - Test cases.xlsx`. The file already contains:
- **TC ID** (Neg_0001 to Neg_0050)
- **Input length type** (S / M / L)
- **Input** (Singlish text)
- **Expected output** (correct Sinhala)
- **Singlish input types covered**
- **Evidence or rationale**

> ⚠️ Do **NOT** manually fill the `Actual output` or `Status` columns — the script fills these automatically.

### Step 2 – Run the Playwright script

Open a terminal / Command Prompt and navigate to the project folder:

```bash
cd test_automation
```

Then run:

```bash
python test_automation.py --excel "test_automation/Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Step 3 – Check results

After the script finishes, reopen the Excel file and verify the **Actual output** and **Status** columns have been filled in automatically.

---

## Command-Line Options

| Option | Default | Description |
|--------|---------|-------------|
| `--excel` | `Assignment 1 - Test cases.xlsx` | Path to the Excel test cases file |
| `--url` | `https://www.pixelssuite.com/chat-translator` | URL of the translator app |
| `--wait-ms` | `5000` | Wait time (ms) after each transliteration |
| `--type-delay-ms` | `80` | Typing delay (ms) per character |
| `--slow-mo-ms` | `200` | Browser slow motion delay (ms) |
| `--save-every` | `1` | Save Excel after every N test cases |
| `--keep-open` | `false` | Keep browser open after tests complete |
| `--headless` | `false` | Run browser without UI |

---

## Test Coverage

The 50 test cases cover all **24 Singlish input types** specified in Appendix 1:

| # | Singlish Input Type | Test Cases |
|---|---|---|
| 1 | Question forms | Neg_0001, Neg_0002 |
| 2 | Command forms | Neg_0003, Neg_0004 |
| 3 | Greetings | Neg_0005, Neg_0006 |
| 4 | Requests | Neg_0007, Neg_0008 |
| 5 | Responses | Neg_0009, Neg_0010 |
| 6 | Repeated Words | Neg_0011, Neg_0012 |
| 7 | Inputs with Punctuation Marks | Neg_0013, Neg_0014 |
| 8 | Romanization / Spelling Variants | Neg_0015, Neg_0016 |
| 9 | Isolated English Word Insertions | Neg_0017, Neg_0018 |
| 10 | Multi-Word English Phrases | Neg_0019, Neg_0020 |
| 11 | English Digital Terms | Neg_0021, Neg_0022 |
| 12 | Platform/App Names | Neg_0023, Neg_0024 |
| 13 | English Abbreviations/Acronyms | Neg_0025, Neg_0026 |
| 14 | English Clipped Forms | Neg_0027, Neg_0028 |
| 15 | Place Names Embedded | Neg_0029, Neg_0030 |
| 16 | Person Names Embedded | Neg_0031, Neg_0032 |
| 17 | Inputs with Numbers & Numeric Suffixes | Neg_0033, Neg_0034 |
| 18 | Inputs with Currency | Neg_0035, Neg_0036 |
| 19 | Inputs with Time Formats | Neg_0037, Neg_0038 |
| 20 | Inputs with Dates | Neg_0039, Neg_0040 |
| 21 | Inputs with Unit of Measurements | Neg_0041, Neg_0042 |
| 22 | Inputs with Slang and Casual Phrasing | Neg_0043, Neg_0044 |
| 23 | Online Identifiers in Singlish | Neg_0045, Neg_0046 |
| 24 | Inputs Containing Emojis | Neg_0047, Neg_0048 |
| – | Mixed / any types (extra 2) | Neg_0049, Neg_0050 |

---

## Notes

- All 50 test cases are **negative** (FAIL) scenarios — inputs where the system produces incorrect Sinhala output.
- TC IDs begin with `Neg_` as required.
- Input length types: **S** (≤30 chars), **M** (31–299 chars), **L** (300–450 chars).
- None of the test inputs are copied from Appendix 1 or Appendix 2 examples.

## Author

**MALMI D.H**  
**Registration Number:** IT23819306  
**Module:** IT3040 – IT Project Management  
**Programme:** BSc (Hons) in Information Technology  
**Institution:** Sri Lanka Institute of Information Technology (SLIIT)
