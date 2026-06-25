# B2B Lead Generation & Property Acquisitions Tracker
An interactive, automated Excel pipeline designed for Real Estate Investment Trusts (REITs), acquisitions managers, and real estate wholesalers to track, manage, and optimize property lead flows.

## 📌 Project Overview
This project serves as a comprehensive **Proof of Work** showcasing advanced administrative data management, CRM pipeline architecture, and workflow automation. The tracker processes raw real estate leads, normalizes contact information, and utilizes multi-layered Excel logic to dynamically link properties to public records while providing real-time visual tracking for acquisition teams.

## 📊 Core Features & Architectural Design

### 1. Data Normalization & Structural Integrity
* **Standardized Phone Logging:** Leveraged strict text-escaped data entry strings (`'+1...`) to preserve global phone formatting standards, eliminating truncation or exponential notation errors common in Excel.
* **Financial Data Masking:** Applied explicit `$` accounting currency formatting across estimated property values to ensure immediate scannable asset valuation.

### 2. Interactive Pipeline & Visual Telemetry
* **Restricted Data Validation:** Built bulletproof dropdown menus using strict in-line validation rules mapping to specific lead lifecycles: `New Lead`, `Cold Called`, `Warm Lead`, and `Appointment Set`. This prevents human data-entry errors and keeps data pristine for CRM uploading.
* **Dynamic Conditional Formatting:** Engineered automated visual logic rules. The moment a user selects a status from the dropdown menu, the cell instantly reads the text value and shifts its color palette to reflect the real-time priority:
  * 🔵 **Blue:** New Lead (Untouched)
  * 🔘 **Grey:** Cold Called (Contact Initiated)
  * 🟡 **Yellow:** Warm Lead (Nurturing/High Interest)
  * 🟢 **Green:** Appointment Set (Active Pipeline/Conversion)

### 3. Dynamic API-Style Resource Linking
* **Zero-Manual-Search URL Generation:** Avoided time-consuming manual link hunting by embedding a nested string manipulation formula in the **Zillow/Redfin Link** column:
  ```excel
  =HYPERLINK("https://www.zillow.com/homes/" & SUBSTITUTE(B5, " ", "-"), "View on Zillow")
