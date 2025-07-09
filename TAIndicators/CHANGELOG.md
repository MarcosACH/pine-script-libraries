# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2025-06-17

### ⚠️ BREAKING CHANGES

**Please be aware that these are BREAKING CHANGES.** You will need to update any of your existing scripts that use these functions to ensure they continue to work correctly.

### Changed

#### 1. Standardized Returns for ma(), atr(), and obv()

To make the library more predictable and robust, the **ma()**, **atr()**, and **obv()** functions have been refactored.

**Old Behavior:** These functions used to return a single value or a list of values depending on the parameters used.

**New Behavior:** They will **always** return a complete list (a tuple) of all possible outputs. If an output is not applicable (e.g., you don't request smoothing), its place in the list will now be filled with **na**.

**Action Required:** You must update how you call these functions to receive a list.

**Example for ma():**

- **Old Code:**

```pinescript
// This will no longer work  
mySimpleMa = calc.ma("SMA", close, 20)  
```

- **New Code:**

```pinescript
// You must now receive the full list of returned values.  
// Use the underscore _ to ignore any values you don't need.  
[mySimpleMa, _, _, _] = calc.ma("SMA", close, 20)  
```

The same logic applies to the **atr()** and **obv()** functions. This change ensures a consistent and predictable output every time you call the function.

### Added

#### 2. New Pivot Outputs for rsi()

The **rsi()** function has been enhanced to be even more useful for divergence and price action analysis.

**New Feature:** In addition to divergence booleans, **rsi()** now also returns two new booleans at the end of its output list:

- A boolean indicating a **pivot low** has been found on the RSI.
- A boolean indicating a **pivot high** has been found on the RSI.

**Action Required:** Because new values have been added to the output list, you must update your code to account for them.

**Example for rsi():**

- **Old Code:**

```pinescript
// This will cause a compiler error now  
[rsiVal, smoothRsi, _, _, bullDiv, bearDiv] = calc.rsi(close, 14, "EMA", 10)  
```

- **New Code:**

```pinescript
// Add variables for the new pivot outputs at the end.  
[rsiVal, smoothRsi, _, _, bullDiv, bearDiv, isPivotLow, isPivotHigh] = calc.rsi(close, 14, "EMA", 10)  
```

## Migration Guide

Please update your scripts accordingly to take advantage of these improvements. These changes make the library more stable and feature-rich for everyone.

As always, thank you for your support!
