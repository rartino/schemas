# are, a (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/are`](https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/are)**  
**Definition name:** `are`

**Unit name:** are  
**Latin symbol:** a  
**Display symbol:** a  
  
**Description:** A unit of area equal to 100 square meters (10² m²), with meter defined according to the 1960 SI base units.

The are appear in the International System of Units (SI), 1th ed. (1970) defined as "1 a = 1 dam² = 10² m²" with the footnote "This unit and its symbol were adopted by the International Committee in 1879 (Proces-Verbaux C.I.P.M., 1879, p. 41).

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "units in use temporarily".
The International System of Units (SI), 5th ed. (1985) adds the clarification that the unit is "used to express agricultural areas."
The International System of Units (SI), 8th ed. (2006) completely removes the unit (but still defines the hectare).
The International System of Units (SI), 7th ed. (1998) reintroduces the unit in the category "Other non-SI units currently accepted for use with the International System."

**Resources:**

- [Definition in the International System of Units (SI), 1th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Hectare#Are)


**Formats:** [[JSON](are.json)] [[MD](are.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/are",
    "title": "are",
    "symbol": "a",
    "display-symbol": "a",
    "description": "A unit of area equal to 100 square meters (10\u00b2 m\u00b2), with meter defined according to the 1960 SI base units.\n\nThe are appear in the International System of Units (SI), 1th ed. (1970) defined as \"1 a = 1 dam\u00b2 = 10\u00b2 m\u00b2\" with the footnote \"This unit and its symbol were adopted by the International Committee in 1879 (Proces-Verbaux C.I.P.M., 1879, p. 41).\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"units in use temporarily\".\nThe International System of Units (SI), 5th ed. (1985) adds the clarification that the unit is \"used to express agricultural areas.\"\nThe International System of Units (SI), 8th ed. (2006) completely removes the unit (but still defines the hectare).\nThe International System of Units (SI), 7th ed. (1998) reintroduces the unit in the category \"Other non-SI units currently accepted for use with the International System.\"",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "hectare"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 1th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Hectare#Are"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "m",
                "id": "https://schema.optimade.org/units/v1.2.0/si/2019/base/metre"
            }
        ],
        "base-units-expression": "m^2",
        "scale": {
            "exponent": 4
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "are"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```