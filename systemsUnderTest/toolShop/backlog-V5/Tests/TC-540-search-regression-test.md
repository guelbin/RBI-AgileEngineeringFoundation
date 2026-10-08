# Test Case: Verify that unrelated products are not shown in search results for "Pliers"

## Objective

Verify that searching for "Pliers" returns only relevant products and excludes unrelated items such as "Leather toolbelt".

---

## Preconditions

* The Toolshop demo application is accessible
* Browser is open
* Test data contains plier products
* Test data contains the product "Leather toolbelt"

---

## Test Data

* Search term: **Pliers**

---

## Test Steps

### Step 1

**Action:**
Open the Toolshop demo application:
https://practicesoftwaretesting.com/

**Expected Result:**
The homepage is loaded successfully.

---

### Step 2

**Action:**
Enter "Pliers" into the search field.

**Expected Result:**
The search input accepts the value "Pliers".

---

### Step 3

**Action:**
Click the Search button.

**Expected Result:**
The search results are displayed.

---

### Step 4

**Action:**
Review the search results.

**Expected Result:**
Only relevant plier products are displayed.

---

### Step 5

**Action:**
Verify that "Leather toolbelt" is not displayed in the search results.

**Expected Result:**
The product "Leather toolbelt" is not visible in the results.

---

### Step 6

**Action:**
Verify that relevant plier products are displayed.

**Expected Result:**
"4 products found for 'pliers'"  is displayed

---

### Step 7

**Action:**
Check the number of displayed search results.

**Expected Result:**
The number matches the visible relevant products.

---

## Test Type

* Regression Test

---

## Priority

* High

---

## Automation

* Automation Candidate: Yes
* Suggested Tool: Playwright

---

## Notes

This test case can be used as input for automated testing to verify search result relevance.
