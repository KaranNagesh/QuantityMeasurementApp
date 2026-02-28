# Quantity Measurement App - UC14 (Temperature Measurement with Selective Arithmetic Support)

## 📌 Overview

- UC14 extends the Quantity Measurement Application to support temperature measurements while respecting real-world arithmetic constraints.
- Unlike length, weight, and volume, temperature does not support full arithmetic.
- This use case refactors the IMeasurable interface to make arithmetic optional, enabling temperature units to support only equality and conversion while rejecting unsupported operations with clear errors.

## ⚙️ Use Case: UC14 (Temperature Measurement)

- Introduces **temperature measurement support** with unit conversion and equality
- Restricts **unsupported arithmetic operations** on temperature with clear validation
- Refactors `IMeasurable` to allow **selective operation support** while keeping existing units unchanged

## ⚙️ UC14 – Key Implementation Points

* Introduced `TemperatureUnit` (Celsius, Fahrenheit, Kelvin) with non-linear conversion formulas.
* Refactored `IMeasurable` to add `default methods` for optional arithmetic support.
* Added **SupportsArithmetic** functional interface with lambda-based capability flags.
* Non-temperature units inherit default arithmetic support (**backwards compatible**).
* Temperature explicitly **disables arithmetic** (add, subtract, divide) via overrides.
* `Quantity` validates `operation support upfront` before performing arithmetic.
* Equality and conversion work uniformly via **base-unit normalisation**.
* Cross-category comparisons remain `prohibited and type-safe`.
* Unsupported operations fail fast with **clear UnsupportedOperationException** messages.
* All **UC1–UC13 tests pass unchanged**, ensuring non-breaking evolution.

  [Source Code](https://github.com/KaranNagesh/QuantityMeasurementApp/tree/feature/UC14-TemperatureMeasurement)

---
