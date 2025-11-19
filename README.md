# umarraza78.github.io

# Assignment 4: Interactive Smart Sale Calculator

## 1. Overview
[cite_start]This project is a single-page web application built to simulate a real-world software failure[cite: 1]. It functions as a "Smart Sale Calculator" that determines the final price of a product after a discount is applied.

## 2. Selected Failure Option
* [cite_start]**Option:** Option B - Software Bug / Glitch (simulated) 
* **Failure Type:** Logical Regression (Wrong Formula)
* **Description:** Under normal operation ("Happy Path"), the app subtracts the discount percentage from the price. [cite_start]When the failure is toggled, the app switches to an incorrect formula that *adds* the discount to the price[cite: 21].

## 3. How to Run
1.  Ensure you have the `index.html` file.
2.  Open `index.html` in any modern web browser (Google Chrome, Firefox, Edge).
3.  To view the logs, right-click anywhere on the page, select **Inspect**, and navigate to the **Console** tab.

## 4. How to Trigger the Failure
1.  **Happy Path (Normal):** * Ensure the "Simulate Bug" toggle at the bottom is **OFF** (Formula preview shows `price * (1 - discount)`).
    * Enter a Price (e.g., 100) and Discount (e.g., 20).
    * Click "Calculate Price".
    * **Result:** $80.00 (Correct).

2.  **Failure Path (Bug):**
    * Turn the "Simulate Bug" toggle **ON**.
    * Observe the formula preview change to red: `price * (1 + discount)`.
    * Click "Calculate Price".
    * [cite_start]**Result:** The screen will shake, inputs turn red, and a crash banner will appear stating "Calculation anomaly detected"[cite: 22].
    * **Log:** A structured JSON error log will be printed to the browser console.

## 5. Expected Log Example

```json
{
  "timestamp": "2025-11-19T12:00:00.000Z",
  "function": "calculate",
  "input": {
    "price": 100,
    "discount": 20
  },
  "result": 120,
  "expected": 80,
  "delta": 40,
  "errorCode": "BUG_WRONG_FORMULA"
}
