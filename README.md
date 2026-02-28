# Quantity Measurement App – UC11 (VolumeMeasurement)

### 📌 Overview

- This module extends the Quantity Measurement Application to support **volume measurements** (litres, millilitres, gallons).
- It demonstrates equality comparison, unit conversion, and addition operations for volume, leveraging the generic `Quantity<U>` class and `IMeasurable` interface. - Volume is treated as a separate category from length and weight, validating the scalability of the generic architecture.

### ⚙️ Use Case:  UC11 – Volume Measurement Equality, Conversion, and Addition

- Accepts numerical values with their respective volume units (LITRE, MILLILITRE, GALLON)
- Compares volumes for equality
- Converts between volume units
- Adds two volume quantities, optionally specifying a target unit

### ⚙️ Key Implementation Points

- `VolumeUnit` enum implements `IMeasurable` with LITRE as the base unit
- Conversion factors: MILLILITRE = 0.001 L, GALLON ≈ 3.78541 L
- Equality uses base unit comparison with epsilon tolerance
- Generic `Quantity<U>` handles conversion and addition without modification
- Maintains type safety: volume cannot be mixed with length or weight
- Objects are immutable; addition and conversion return new instances
