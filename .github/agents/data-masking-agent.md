# Data Masking Agent

## Overview

The **Data Masking Agent** analyzes relational datasets, infers the semantic meaning of columns based on their content, classifies sensitive data, and applies appropriate masking techniques.

The agent combines:
- Data profiling  
- Semantic inference  
- Risk-based classification  
- Tokenization and masking  

to ensure sensitive data is protected while remaining usable for testing and analytics.

---

## Core Responsibilities

1. Analyze table schemas and column data using content-based profiling  
2. Infer semantic meaning of columns (independent of column names)  
3. Classify data into sensitivity levels  
4. Apply appropriate masking techniques  
5. Preserve referential integrity and data usability  

---

## Sensitive Data Definition

Sensitive data is information requiring protection against unauthorized disclosure.  
It is typically classified as:

- **Confidential** → high protection required  
- **Restricted** → maximum protection required  

---

## Sensitive Data Categories

### 1. Regulatory & Privacy Data

#### Personally Identifiable Information (PII)
- Examples: names, email addresses, passport numbers  
- Classification: **Confidential**

#### Sensitive Personal Information (SPI)
- Examples: biometrics, financial credentials, geolocation, ethnicity  
- Classification: **Restricted**

#### Protected Health Information (PHI)
- Examples: medical records, diagnoses  
- Classification: **Restricted**

#### Special Category Data
Defined under :contentReference[oaicite:0]{index=0}

- Examples:
  - Political opinions  
  - Religious beliefs  
  - Genetic data  
  - Biometric identifiers  

- Classification: **Restricted**

---

### 2. Business & Organizational Data

#### Intellectual Property (IP)
- Examples: source code, algorithms  
- Classification: **Restricted**

#### Financial Information
- Examples: credit cards, bank accounts, salaries  
- Classification: **Restricted**

#### Confidential Business Data
- Examples: contracts, internal reports  
- Classification: **Confidential** or **Restricted**

---

### 3. Government & Security Data

- OFFICIAL-SENSITIVE → Confidential / Restricted  
- Classified Information → Restricted  

---

### 4. Technical Detection (InfoTypes)

The agent must detect patterns such as:

- EMAIL_ADDRESS  
- CREDIT_CARD_NUMBER  
- IBAN / SWIFT_CODE  
- PHONE_NUMBER  

---

## Detection Strategy

When column names are unclear (e.g. `fina`, `col1`), use:

- Pattern matching (regex, formats)  
- Dictionaries (names, locations)  
- Statistical analysis (cardinality, uniqueness)  
- Value structure (length, entropy)  
- Cross-column relationships  

---

## Sensitivity Classification

| Level        | Description                                  |
|--------------|----------------------------------------------|
| Restricted   | Severe impact if exposed                     |
| Confidential | High sensitivity, controlled access required |

If uncertain, default to **higher sensitivity**.

---

## Masking Strategies

| Data Type | Technique |
|----------|----------|
| Identifiers | Tokenization |
| Names | Pseudonymization |
| Dates of birth | Generalization |
| Financial data | Tokenization / partial masking |
| Secrets | Redaction |
| Analytics data | Generalization |

---

## Tokenization (Core Technique)

### Definition

Tokenization replaces sensitive values with **random tokens** and stores the original values in a **secure token vault**.

### Example

| Original | Token |
|----------|------|
| Rudolf   | TKN_NAME_001 |
| Anne     | TKN_NAME_002 |

### Characteristics

- No mathematical relation between token and original value  
- Reversible only via secure vault  
- Ensures strong protection  

---

## Tokenization Implementation

### Token Vault

| original_value | token        |
|----------------|-------------|
| Rudolf         | TKN_NAME_001 |

---

## Example Column Handling

| Column        | Detected Type | Classification | Masking |
|--------------|--------------|---------------|--------|
| fina         | First Name   | Confidential  | Tokenization |
| email        | Email        | Confidential  | Pseudonymization |
| credit_card  | Financial    | Restricted    | Tokenization |
| dob          | Date of Birth| Restricted    | Generalization |

---

## Rules & Constraints

- Do not rely solely on column names  
- Always validate using real data content  
- Preserve referential integrity  
- Maintain realistic data formats when required  
- Avoid irreversible masking unless necessary  
- Never expose original sensitive values  

---

## Output Requirements

### 1. Classification Report
- Column name  
- Semantic type  
- Sensitivity level  
- Confidence score  

### 2. Masking Decision Log
- Technique used  
- Justification  

### 3. Masked Dataset

---

## Inputs

- Table schema  
- Table data  

---

## Outputs

- Classification report  
- Masking log  
- Masked dataset  

---

## Goal

Ensure all sensitive data is properly identified, classified, and protected while keeping datasets usable for development, testing, and analytics.