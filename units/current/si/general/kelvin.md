# kelvin, K (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/kelvin`](https://schemas.optimade.org/units/v1.2.0/si/general/kelvin)**  
**Definition name:** `kelvin`

**Unit name:** kelvin  
**Latin symbol:** K  
**Display symbol:** K  
  
**Description:** A unit of thermodynamic temperature using the current, or one of the historical, definitions of the SI units.

The current definition at the 26th CGPM Meeting in 2018, resolution 1 is: "The kelvin, symbol K, is the SI unit of thermodynamic temperature. It is defined by taking the fixed numerical value of the Boltzmann constant k to be 1.380649×10⁻²³ when expressed in the unit J⋅K⁻¹, which is equal to kg⋅m²⋅s⁻²⋅K⁻¹, where the kilogram, metre and second are defined in terms of \(h\), \(c\) and \(\Delta \nu_\textrm{Cs}\)." [26th CGPM Meeting (2018), resolution 1].

The prior definition at the 13th CGPM Meeting in 1967, resolution 4, was: "The kelvin, unit of thermodynamic temperature, is the fraction 1/273.16 of the thermodynamic temperature of the triple point of water."
This definition changed the symbol and rephrased the definition of the unit "degree Kelvin" from the 10th CGPM meeting in 1954: "The 10th Conférence Générale des Poids et Mesures decides to define the thermodynamic temperature scale by choosing the triple point of water as the fundamental fixed point, and assigning to it the temperature 273.16 degrees Kelvin, exactly."

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition in the 26th CGPM Meeting in 2018, resolution 1](https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1)
- [Definition in the International System of Units (SI), 9th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Kelvin)


**Formats:** [[JSON](kelvin.json)] [[MD](kelvin.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/kelvin",
    "title": "kelvin",
    "symbol": "K",
    "display-symbol": "K",
    "description": "A unit of thermodynamic temperature using the current, or one of the historical, definitions of the SI units.\n\nThe current definition at the 26th CGPM Meeting in 2018, resolution 1 is: \"The kelvin, symbol K, is the SI unit of thermodynamic temperature. It is defined by taking the fixed numerical value of the Boltzmann constant k to be 1.380649\u00d710\u207b\u00b2\u00b3 when expressed in the unit J\u22c5K\u207b\u00b9, which is equal to kg\u22c5m\u00b2\u22c5s\u207b\u00b2\u22c5K\u207b\u00b9, where the kilogram, metre and second are defined in terms of \\(h\\), \\(c\\) and \\(\\Delta \\nu_\\textrm{Cs}\\).\" [26th CGPM Meeting (2018), resolution 1].\n\nThe prior definition at the 13th CGPM Meeting in 1967, resolution 4, was: \"The kelvin, unit of thermodynamic temperature, is the fraction 1/273.16 of the thermodynamic temperature of the triple point of water.\"\nThis definition changed the symbol and rephrased the definition of the unit \"degree Kelvin\" from the 10th CGPM meeting in 1954: \"The 10th Conf\u00e9rence G\u00e9n\u00e9rale des Poids et Mesures decides to define the thermodynamic temperature scale by choosing the triple point of water as the fundamental fixed point, and assigning to it the temperature 273.16 degrees Kelvin, exactly.\"\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1967/base/kelvin",
        "https://schemas.optimade.org/units/v1.2.0/si/2019/base/kelvin",
        "https://schemas.optimade.org/units/v1.2.0/si/1960/base/degreekelvin"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "kelvin"
    },
    "resources": [
        {
            "relation": "Definition in the 26th CGPM Meeting in 2018, resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1"
        },
        {
            "relation": "Definition in the International System of Units (SI), 9th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
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