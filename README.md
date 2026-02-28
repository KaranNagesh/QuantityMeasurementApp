# Quantity Measurement App – UC9 (WeightMeasurement)

### 📌 Overview

- This module extends the Quantity Measurement App to support `weight measurements` (kilogram, gram, pound).
- It focuses on correct object equality, unit conversion, addition operations, and safe floating-point comparisons while maintaining immutability and type safety.

### ⚙️ Use Case: UC9 – Weight Measurement Equality, Conversion, and Addition

- Accepts two or more numerical values with `weight units` (kg, g, lb)
- Compares weights for equality
- Converts weights between units
- Adds two weight measurements and returns a new object

### ⚙️ Key Implementation Points

- Uses a **WeightUnit enum** for conversion responsibility (base unit: kilogram)
- Uses a **QuantityWeight class** to represent weight measurements
- Measurement value and unit are **private and final** (immutable)
- `equals()` is overridden to handle cross-unit comparisons
- `convertTo()` method normalises via the base unit
- `add()` methods support implicit (default) and explicit target unit addition
- **Double.compare()** ensures safe floating-point comparison
- Handles null, type mismatch, same reference, and category incompatibility safely
- Weight and length measurements are **distinct categories** and cannot be compared
