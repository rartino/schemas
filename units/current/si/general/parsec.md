# parsec, pc (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/parsec`](https://schemas.optimade.org/units/v1.2.0/si/general/parsec)**  
**Definition name:** `parsec`

**Unit name:** parsec  
**Latin symbol:** pc  
**Display symbol:** pc  
  
**Description:** A unit of length representing the distance at which 1 astronomical unit subtends an angle of 1 arcsecond using the current, or one of the historical, definitions of the SI units.

The parsec appear in the International System of Units (SI), 1th ed. (1970) defined in a footnote as "1 parsec is the distance at which 1 astronomical unit subtends an angle of 1 arcsecond; therefore, approximately, 1 pc = 206 265 AU = 30 857 x 10¹² m.

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "units for use with the SI in specific domains."
The International System of Units (SI), 2th ed. (1973) categorizes the unit as "Non-SI units accepted for use with the International System, whose values in SI units are obtained experimentally."
The International System of Units (SI), 4th ed. (1981) and later editions omit the unit.

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition in the International System of Units (SI), 1st Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Parsec)


**Formats:** [[JSON](parsec.json)] [[MD](parsec.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/parsec",
    "title": "parsec",
    "symbol": "pc",
    "display-symbol": "pc",
    "description": "A unit of length representing the distance at which 1 astronomical unit subtends an angle of 1 arcsecond using the current, or one of the historical, definitions of the SI units.\n\nThe parsec appear in the International System of Units (SI), 1th ed. (1970) defined in a footnote as \"1 parsec is the distance at which 1 astronomical unit subtends an angle of 1 arcsecond; therefore, approximately, 1 pc = 206 265 AU = 30 857 x 10\u00b9\u00b2 m.\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"units for use with the SI in specific domains.\"\nThe International System of Units (SI), 2th ed. (1973) categorizes the unit as \"Non-SI units accepted for use with the International System, whose values in SI units are obtained experimentally.\"\nThe International System of Units (SI), 4th ed. (1981) and later editions omit the unit.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/parsec"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "parsec"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 1st Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Parsec"
        }
    ],
    "approximate-relations": [
        {
            "base-units": [
                {
                    "symbol": "m",
                    "id": "https://schemas.optimade.org/units/v1.2.0/si/general/metre"
                }
            ],
            "scale": {
                "value": 3.0857e+16
            }
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "parsec"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```