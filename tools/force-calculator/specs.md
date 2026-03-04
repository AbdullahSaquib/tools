# Product Specification: Force Calculator

## 1. Overview & Purpose

**Tool Name:** Force Calculator
**Slug:** force-calculator
**Description:** Calculate force using F=ma

This single-page HTML tool provides a web-based interface for calculating force (F) based on user-provided values for mass (m) and acceleration (a), utilizing the fundamental formula F=ma.

## 2. Target Users

Not specified by user responses.

## 3. Core Features & Functionality

*   **Formula:** Calculates force (F) using the formula F=ma.
*   **Input Acceptance:** Accepts numerical values for mass and acceleration.
*   **Internal Calculation Units:** All input mass values must be converted to kilograms (kg) internally for calculation. All input acceleration values must be converted to meters per second squared (m/s²) internally for calculation.
*   **Output Unit:** Displays the calculated force exclusively in Newtons (N).
*   **Real-time Calculation:** Automatically performs the calculation and updates the result as input values are typed by the user.
*   **Output Precision:** The displayed calculated force (F) must use "significant figures" determined by the precision of the input values.
*   **Input Validation - Negative Values:** Disallows the input of negative values for both mass and acceleration, requiring positive values only.
*   **Input Validation - Non-numeric Characters:** Identifies and handles non-numeric characters entered into the mass or acceleration input fields.

## 4. UI/UX Requirements

*   **Input Fields:**
    *   Provide dedicated text input fields for mass.
    *   Provide dedicated text input fields for acceleration.
*   **Unit Selection:**
    *   Each input field (mass and acceleration) must have a separate dropdown menu for unit selection (e.g., kg, g, lb for mass; m/s², ft/s² for acceleration, etc., as implied by "e.g., kg, g, lb").
*   **Initial State:**
    *   Upon page load, both the mass and acceleration input fields must default to '0'.
*   **Invalid Input Handling:**
    *   **Visual Feedback:** If non-numeric characters are entered into an input field, that specific input field must be highlighted in red.
    *   **Calculation Button State:** The calculation button (if present, or the mechanism that triggers calculation) must be disabled when invalid (non-numeric or negative) input is detected in either the mass or acceleration fields.
*   **Calculated Force Display:** The calculated force (F) must be displayed clearly, labeled with the unit "N" (Newtons).

## 5. Technical Requirements

*   **Architecture:** Must be implemented as a single-page HTML tool.
*   **Client-Side Processing:** All calculations, input validation, and UI updates must occur client-side (e.g., using JavaScript).
*   **Input Validation Logic:** Implementation must include logic to:
    *   Check for and reject negative input values for mass and acceleration.
    *   Check for and reject non-numeric characters in input fields.
*   **Unit Conversion Logic:** Implementation must include logic to convert selected input units (e.g., grams, pounds for mass; feet per second squared for acceleration) into the required internal calculation units (kilograms and meters per second squared, respectively).
*   **Precision Algorithm:** An algorithm must be implemented to determine and display the output force (F) with the correct number of significant figures based on the precision of the input values.
*   **Real-time Update Mechanism:** Event listeners (e.g., `onkeyup`, `