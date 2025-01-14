# kelvin, K (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1967/base/kelvin`](https://schemas.optimade.org/units/v1.2.0/si/1967/base/kelvin)**  
**Definition name:** `kelvin`

**Unit name:** kelvin  
**Latin symbol:** kelvin  
**Display symbol:** K  
  
**Description:** The kelvin is the SI base unit of thermodynamic temperature defined from the triple point of water at the 13th CGPM Meeting in 1967, resolution 3 and 4 and clarified at the 23rd CGPM Meeting in 2007, resolution 10.

The definition is functionally the same as the prior definition of degree Kelvin from the 10th CGPM meeting in 1954.
However, at the 13th CGPM Meeting in 1967, resolution 4, the definition was rephrased as: "The kelvin, unit of thermodynamic temperature, is the fraction 1/273.16 of the thermodynamic temperature of the triple point of water."
In this defining text, and as decided in resolution 3, the unit is named kelvin with the symbol K, replacing the prior use of degree Kelvin and variations.

The 23th CGPM meeting in 2007, resolution 10, approved to append a clarification to the above definition: "This definition refers to water having the isotopic composition defined by the following amount-of-substance ratios: 0.00015576 mole of ²H per mole of ¹H, 0.0003799 mole of ¹⁷O per mole of ¹⁶O and 0.0020052 mole of ¹⁸O per mole of ¹⁶O."

**Resources:**

- [Definition at the 13th CGPM meeting (1967), resolution 4](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-4)
- [Definition of the name kelvin and symbol K at the 13th CGPM meeting (1967), resolution 3](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-3)
- [Clarification at the 23th CGPM meeting (2007), resolution 10](https://www.bipm.org/en/committees/cg/cgpm/23-2007/resolution-10)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Kelvin)


**Formats:** [[JSON](kelvin.json)] [[MD](kelvin.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1967/base/kelvin",
    "title": "kelvin",
    "symbol": "kelvin",
    "display-symbol": "K",
    "description": "The kelvin is the SI base unit of thermodynamic temperature defined from the triple point of water at the 13th CGPM Meeting in 1967, resolution 3 and 4 and clarified at the 23rd CGPM Meeting in 2007, resolution 10.\n\nThe definition is functionally the same as the prior definition of degree Kelvin from the 10th CGPM meeting in 1954.\nHowever, at the 13th CGPM Meeting in 1967, resolution 4, the definition was rephrased as: \"The kelvin, unit of thermodynamic temperature, is the fraction 1/273.16 of the thermodynamic temperature of the triple point of water.\"\nIn this defining text, and as decided in resolution 3, the unit is named kelvin with the symbol K, replacing the prior use of degree Kelvin and variations.\n\nThe 23th CGPM meeting in 2007, resolution 10, approved to append a clarification to the above definition: \"This definition refers to water having the isotopic composition defined by the following amount-of-substance ratios: 0.00015576 mole of \u00b2H per mole of \u00b9H, 0.0003799 mole of \u00b9\u2077O per mole of \u00b9\u2076O and 0.0020052 mole of \u00b9\u2078O per mole of \u00b9\u2076O.\"",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1960/base/degreekelvin"
    ],
    "resources": [
        {
            "relation": "Definition at the 13th CGPM meeting (1967), resolution 4",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-4"
        },
        {
            "relation": "Definition of the name kelvin and symbol K at the 13th CGPM meeting (1967), resolution 3",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-3"
        },
        {
            "relation": "Clarification at the 23th CGPM meeting (2007), resolution 10",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/23-2007/resolution-10"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Kelvin"
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "kelvin"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```