# micro, μ (prefix)
This page documents an [OPTIMADE](https://www.optimade.org/) [Prefix Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/prefixes/micro`](https://schemas.optimade.org/units/v1.2.0/si/prefixes/micro)**  
**Definition name:** `micro`

**Prefix name:** micro  
**Latin symbol:** mc  
**Display symbol:** μ  
  
**Description:** The micro SI prefix defined as a dimensionless multiple of 10⁻⁶, adopted into SI at its creation at the 11th CGPM Meeting in 1960, resolution 12.

The micro SI prefix is the only one using a non Latin symbol.
Based on the recommendation of the ISMP List of Error-Prone Abbreviations, Symbols, and Dose Designations to use mcg in place of μg, mc is used for a symbol for micro using the Latin alphabet.

**Resources:**

- [Definition in the 11:th CGPM Meeting in 1960, resolution 12](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Use of mc to represent micro in the ISMP List of Error-Prone Abbreviations, Symbols, and Dose Designations](https://www.ismp.org/recommendations/error-prone-abbreviations-list)
- [Wikipedia article describing the prefix](https://en.wikipedia.org/wiki/Micro-)


**Formats:** [[JSON](micro.json)] [[MD](micro.md)]

**JSON definition:**

``` json
{
    "title": "micro",
    "symbol": "mc",
    "display-symbol": "\u03bc",
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/prefixes/micro",
    "description": "The micro SI prefix defined as a dimensionless multiple of 10\u207b\u2076, adopted into SI at its creation at the 11th CGPM Meeting in 1960, resolution 12.\n\nThe micro SI prefix is the only one using a non Latin symbol.\nBased on the recommendation of the ISMP List of Error-Prone Abbreviations, Symbols, and Dose Designations to use mcg in place of \u03bcg, mc is used for a symbol for micro using the Latin alphabet.",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "micro"
    },
    "resources": [
        {
            "relation": "Definition in the 11:th CGPM Meeting in 1960, resolution 12",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Use of mc to represent micro in the ISMP List of Error-Prone Abbreviations, Symbols, and Dose Designations",
            "resource-id": "https://www.ismp.org/recommendations/error-prone-abbreviations-list"
        },
        {
            "relation": "Wikipedia article describing the prefix",
            "resource-id": "https://en.wikipedia.org/wiki/Micro-"
        }
    ],
    "defining-relation": {
        "base-units": [],
        "base-units-expression": "",
        "scale": {
            "exponent": -6
        }
    },
    "x-optimade-definition": {
        "kind": "prefix",
        "format": "1.2",
        "version": "1.2.0",
        "name": "micro"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```