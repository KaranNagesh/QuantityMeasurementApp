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
```
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
```
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

📅 18 Feb 2026  

**🔹 UC2 – Feet and Inches Equality Verification  **
Branch: feature/UC2-InchEquality

🎯 Objective

- Extend UC1 to check equality of measurements in Inches along with Feet
- Ensure proper equals() logic for both units
- Maintain Test-Driven Development approach

✅ Implementation

- Defined Inches class alongside Feet class
- Added equality logic for Inches using Double.compare()
- Validated numeric input for both units
- Ensured null safety and type validation
- Reduced main method dependency by creating dedicated methods for Feet and Inches equality
- Created JUnit 5 test cases covering same and different values, nulls, and self-reference


[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC2-InchEquality)

---

📅 19 Feb 2026  

**🔹 UC3 – Generic Quantity Class for DRY Principle  **
Branch: feature/UC3-GenericLength

🎯 Objective

- Refactor Feet and Inches classes into a single QuantityLength class
- Apply DRY principle to remove code duplication
- Maintain all equality and conversion functionality from UC1 & UC2
- Enable easy extension for new units

✅ Implementation

- Introduced LengthUnit enum for all supported units and conversion factors
- Created QuantityLength class handling value + unit
- Centralized equality logic using base unit conversion
- Ensured type safety, null handling, and numeric validation
- Added comprehensive JUnit 5 tests for same-unit, cross-unit, and invalid inputs
- All previous UC1 & UC2 functionality preserved

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC3-GenericLength)

---

📅 20 Feb 2026

**🔹 UC4 – Extended Unit Support (Yards & Centimeters)  **
Branch: feature/UC4-YardEquality

🎯 Objective

- Extend QuantityLength class to support Yards and Centimeters
- Maintain cross-unit equality comparisons
- Preserve all previous UC1–UC3 functionality
- Ensure DRY principle while adding new units

✅ Implementation

- Added YARDS and CENTIMETERS to LengthUnit enum with proper conversion factors
- Verified QuantityLength equals() method works seamlessly for new units
- Ensured type safety, numeric validation, and null handling
- Covered yard-to-yard, yard-to-feet, yard-to-inches, and cm conversions in JUnit 5 tests
- All previous tests from UC1–UC3 continue to pass

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC4-YardEquality)

---
📅 20 Feb 2026  

**🔹 UC5 – Unit-to-Unit Conversion (Same Measurement Type)  **
Branch: feature/UC5-UnitConversion

🎯 Objective

- Provide explicit conversion between units (feet ↔ inches, yards ↔ feet, centimeters ↔ inches, etc.)
- Maintain DRY principle and preserve UC1–UC4 functionality
- Expose a standard convert() API for all supported units
- Ensure bidirectional and precise conversions with proper validation

✅ Implementation

- Added static convert(value, sourceUnit, targetUnit) method in QuantityLength
- Validates numeric value and non-null, supported source/target units
- Normalizes input to base unit (feet) before converting to target unit
- Overloaded demonstrateLengthConversion() for raw values and QuantityLength instances
- Ensured proper rounding, epsilon tolerance, and exception handling for invalid inputs
- Preserved equals() and toString() overrides for consistent object behavior
- Comprehensive JUnit 5 tests cover same-unit, cross-unit, negative, zero, large, and small conversions

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC5-UnitConversion)

---

📅 21 Feb 2026  

**🔹 UC6 – Addition of Two Length Units (Same Category)  **
Branch: feature/UC6-UnitAddition

🎯 Objective

- Enable addition of two QuantityLength objects, potentially with different units
- Result is expressed in the unit of the first operand
- Maintain DRY, immutability, and cross-unit precision

✅ Implementation

- Added instance and static add() methods in QuantityLength
- Validates non-null operands, valid LengthUnits, and finite values
- Converts both operands to base unit (feet), performs addition
- Converts sum to the unit of the first operand
- Returns a new QuantityLength object (immutability preserved)
- Leverages UC5 conversion logic; no duplication of conversion code
- Overloaded methods to support raw values or QuantityLength objects
- Handles zero, negative, large, and small values
- Comprehensive JUnit 5 tests cover same-unit, cross-unit, commutativity, and precision

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC6-UnitAddition/src)

---

📅 21 Feb 2026  
**🔹 UC7 – Addition with Target Unit Specification ** 
Branch: feature/UC7-TargetUnitAddition

🎯 Objective

- Extend UC6 addition functionality by allowing an explicit target unit
- Result can be expressed in any supported LengthUnit, not just the first operand
- Maintain immutability, precision, and cross-unit consistency

✅ Implementation

- Overloaded `add()` methods in `QuantityLength` to accept an explicit target unit
- Validates non-null operands, valid LengthUnits, and finite values
- Converts both operands to a base unit (feet), performs addition
- Converts the sum to the specified target unit
- Returns a new `QuantityLength` object (immutability preserved)
- Reuses private utility addition method to avoid code duplication
- Supports both implicit (first operand unit) and explicit target unit addition
- Handles zero, negative, large, and small values
- Ensures commutativity: add(A, B, targetUnit) = add(B, A, targetUnit)
- Comprehensive JUnit 5 tests cover same-unit, cross-unit, and all target unit combinations

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC7-TargetUnitAddition/src)

---

**🔹 UC8: Refactoring LengthUnit to Standalone Enum**  

Description
Extracts `LengthUnit` from inside `QuantityLength` into a standalone top-level class. Assigns conversion responsibility to the enum itself. `QuantityLength` is simplified to delegate all conversions to unit methods. All UC1–UC7 functionality preserved.

Flow
1. `LengthUnit` enum handles `convertToBaseUnit()` and `convertFromBaseUnit()`.
2. `QuantityLength` delegates all conversions to unit methods.
3. Public API remains unchanged → backward compatible.

Key Concepts
- Single Responsibility: `LengthUnit` converts, `QuantityLength` compares/adds
- Eliminates circular dependency for multi-category scaling
- Pattern template for future `WeightUnit`, `VolumeUnit`, etc.


[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC8-StandAloneUnit)

---

** 🔹UC9: Weight Measurement (Equality, Conversion & Addition)** 

Description
Introduces a new `WeightUnit` enum and `QuantityWeight` class mirroring the UC8 length pattern. Supports equality, conversion, and addition for KILOGRAM, GRAM, and POUND. Weight and length are incompatible categories.

Conversion Factors (base: KILOGRAM)
| Unit | Factor |
|------|--------|
| KILOGRAM | 1.0 |
| GRAM | 0.001 |
| POUND | 0.453592 |

Key Concepts
- `WeightUnit` standalone enum with `convertToBaseUnit()` / `convertFromBaseUnit()`
- Category type safety: `Quantity(1.0, KG).equals(Quantity(1.0, FOOT))` → `false`
- Overloaded `add()`: implicit (first operand unit) and explicit (target unit)
- `hashCode()` overridden consistently with `equals()`


[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC9-WeightMeasurement)

---

**🔹UC10: Generic Quantity Class with IMeasurable Interface**

## Description
Refactors `QuantityLength` and `QuantityWeight` into a single generic `Quantity<U extends IMeasurable>` class. Eliminates code duplication across categories using a common interface. All UC1–UC9 functionality preserved.

Architecture
| Component | Responsibility |
|-----------|---------------|
| `IMeasurable` | Defines unit conversion contract |
| `LengthUnit` / `WeightUnit` | Implement `IMeasurable` with conversion factors |
| `Quantity<U>` | Handles equality, conversion, addition for any unit |
| `QuantityMeasurementApp` | Generic demonstration only |

Key Concepts
- Bounded type parameter `<U extends IMeasurable>` for compile-time type safety
- Cross-category prevention via `unit.getClass()` comparison
- `equals()`, `convertTo()`, `add()` implemented once — reused for all categories
- Adding new categories requires ONLY a new enum implementing `IMeasurable`

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC10-MultiCategoryUnit)

---
**🔹UC11: Volume Measurement (Litre, Millilitre, Gallon)** 

 Description
Adds a third measurement category — volume — by creating a `VolumeUnit` enum implementing `IMeasurable`. No changes to `Quantity<U>`, `QuantityMeasurementApp`, or existing tests required. Proves the UC10 architecture scales linearly.

 Conversion Factors (base: LITRE)
| Unit | Factor |
|------|--------|
| LITRE | 1.0 |
| MILLILITRE | 0.001 |
| GALLON | 3.78541 |

 Key Concepts
- Only a new enum needed to add a full measurement category
- Cross-category safety: `1.0 LITRE ≠ 1.0 KILOGRAM` and `1.0 LITRE ≠ 1.0 FOOT`
- All generic `Quantity<U>` operations work automatically

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC11-VolumeMeasurement)

---

** UC12: Subtraction and Division Operations**

 Description
Extends `Quantity<U>` with subtraction (returns `Quantity<U>`) and division (returns dimensionless `double`). Both operations support cross-unit arithmetic within the same category and maintain immutability.

 Operations
| Method | Returns | Notes |
|--------|---------|-------|
| `subtract(other)` | `Quantity<U>` | Result in first operand's unit |
| `subtract(other, targetUnit)` | `Quantity<U>` | Result in explicit unit |
| `divide(other)` | `double` | Dimensionless ratio |

 Key Concepts
- Subtraction is **non-commutative**: `A - B ≠ B - A`
- Division is **non-commutative**: `A ÷ B ≠ B ÷ A`
- Division by zero throws `ArithmeticException`
- Cross-category operations throw `IllegalArgumentException`

[Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC12-ArithmeticUnit)

---
