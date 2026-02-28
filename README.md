# Quantity Measurement App - UC12 (ArithmeticOperations)

### 📌 Overview

- UC12 extends the Quantity Measurement Application by `adding subtraction` and `division operations` to the `generic Quantity<U> model`.
- It builds on `UC1–UC11` and enables full arithmetic manipulation while preserving immutability, type safety, and cross-unit support.

### ⚙️ Use Case: UC12 – Quantity Subtraction & Division

- Subtract two quantities of the same measurement category
- Divide two quantities to obtain a dimensionless ratio
- Support `cross-unit` arithmetic (e.g., feet ↔ inches, litre ↔ millilitre)
- Prevent `cross-category` operations (e.g., length vs weight)

### ⚙️Key Implementation Points

 - Convert operands to base unit before arithmetic
- Validate:
    - Null operands
    - Same measurement category
    - Finite numeric values
    - Division by zero
- Implicit target unit → first operand’s unit
- Explicit target unit supported
- Results rounded to two decimal places (subtraction only)
