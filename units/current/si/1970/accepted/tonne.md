# tonne, t (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/tonne`](https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/tonne)**  
**Definition name:** `tonne`

**Unit name:** tonne  
**Latin symbol:** t  
**Display symbol:** t  
  
**Description:** A unit of mass defined as 1000 kg, with kilogram defined according to the 1960 SI units.

The International System of Units (SI), 1st ed. (1970) defines the tonne as "1 t = 10³ kg" with the footnote "The symbol and the unit was defined in resolution 7 at the 9:th meeting of the C.G.P.M. (1948)."

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "Units used with the International System"
The International System of Units (SI), 3rd ed. (19) changes the reference of the definition to the 1879 meeting of the CIPM page 41.
The International System of Units (SI), 6st ed. (1991) further adds "In some English-speaking countries this unit is called ≪metric ton≫."

**Resources:**

- [Definition in the International System of Units (SI), 1th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Tonne)


**Formats:** [[JSON](tonne.json)] [[MD](tonne.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/tonne",
    "title": "tonne",
    "symbol": "t",
    "display-symbol": "t",
    "alternate-symbols": [
        "t"
    ],
    "description": "A unit of mass defined as 1000 kg, with kilogram defined according to the 1960 SI units.\n\nThe International System of Units (SI), 1st ed. (1970) defines the tonne as \"1 t = 10\u00b3 kg\" with the footnote \"The symbol and the unit was defined in resolution 7 at the 9:th meeting of the C.G.P.M. (1948).\"\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"Units used with the International System\"\nThe International System of Units (SI), 3rd ed. (19) changes the reference of the definition to the 1879 meeting of the CIPM page 41.\nThe International System of Units (SI), 6st ed. (1991) further adds \"In some English-speaking countries this unit is called \u226ametric ton\u226b.\"",
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 1th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Tonne"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "kg",
                "id": "https://schema.optimade.org/units/v1.2.0/si/1960/base/kilogram"
            }
        ],
        "base-units-expression": "kg",
        "scale": {
            "exponent": 3
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "tonne"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```