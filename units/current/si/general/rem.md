# Roentgen equivalent man, rem (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/rem`](https://schemas.optimade.org/units/v1.2.0/si/general/rem)**  
**Definition name:** `rem`

**Unit name:** Roentgen equivalent man  
**Latin symbol:** rem  
**Display symbol:** rem  
  
**Description:** The "roentgen equivalent man" (rem) is a unit used in radioprotection meant to represent a dose of any ionizing radiation comparable in effect to one roentgen of high-voltage x-radiation, taken to be equal to 10⁻² Sv using the current, or one of the historical, definitions of the SI units.

The rem appear in the International System of Units (SI), 4th ed. (1981) defined as "1 rem = 1 cSv = 10⁻² Sv" with the footnote: "The rem is a special unit used in radioprotection to express the equivalent dose."

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition in the International System of Units (SI), 4th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Roentgen_equivalent_man)


**Formats:** [[JSON](rem.json)] [[MD](rem.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/rem",
    "title": "Roentgen equivalent man",
    "symbol": "rem",
    "display-symbol": "rem",
    "description": "The \"roentgen equivalent man\" (rem) is a unit used in radioprotection meant to represent a dose of any ionizing radiation comparable in effect to one roentgen of high-voltage x-radiation, taken to be equal to 10\u207b\u00b2 Sv using the current, or one of the historical, definitions of the SI units.\n\nThe rem appear in the International System of Units (SI), 4th ed. (1981) defined as \"1 rem = 1 cSv = 10\u207b\u00b2 Sv\" with the footnote: \"The rem is a special unit used in radioprotection to express the equivalent dose.\"\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1981/temporary/rem"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "rem"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 4th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Roentgen_equivalent_man"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "kg",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/general/kilogram"
            },
            {
                "symbol": "m",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/general/metre"
            },
            {
                "symbol": "s",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/general/second"
            }
        ],
        "base-units-expression": "kg*m^2*s^-2",
        "scale": {
            "exponent": -2
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "rem"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```