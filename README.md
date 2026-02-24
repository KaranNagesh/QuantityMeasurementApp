# Quantity Measurement Application
### Project Overview
#### The Quantity Measurement Application validates equality, unit conversions, and arithmetic operations across multiple measurement categories:

 - Length: Feet, Inches, Yards, Centimeters
 - Weight: Kilogram, Gram, Pound
##### The project follows best practices:

✅ Test-Driven Development (TDD) ✅ Feature Branch Workflow ✅ Clean Code Practices ✅ DRY (Don’t Repeat Yourself) Principle ✅ Robust Unit Conversion Strategy ✅ Multi-category Measurement Architecture

---
### Git WorkFLow
---
it Workflow
main
 └── dev
      ├── feature/UC1-FeetEquality
      ├── feature/UC2-InchEquality
      ├── feature/UC3-GenericQuantityClassForDRYPrinciple
      ├── feature/UC4-Extended-Unit-Support
      ├── feature/UC5-Unit-to-Unit-Conversion
      ├── feature/UC6-Addition-Of-Two-Length-Units
      ├── feature/UC7-Addition-With-Target-Unit-Specification
      ├── feature/UC8-StandaloneUnit-Refactoring
      └── feature/UC9-WeightMeasurement

---
### Feature History
*📅 17 Feb 2026*

#### 🔹 UC1 – Feet Equality Verification
Branch: feature/UC1-FeetEquality

🎯 Objective

 - Check if two measurements in Feet are equal
 -Correctly override equals() for comparison
 - Apply Test-Driven Development principles

✅ Implementation

 - Defined Feet class for encapsulating measurement
 - Added precise equality logic using Double.compare()
 -Ensured null safety and type validation
 - Created comprehensive JUnit 5 tests
 - 
 [Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC1-FeetEquality)

---
