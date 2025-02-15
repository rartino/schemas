# bar, bar (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/bar`](https://schemas.optimade.org/units/v1.2.0/si/general/bar)**  
**Definition name:** `bar`

**Unit name:** bar  
**Latin symbol:** bar  
**Display symbol:** bar  
  
**Description:** A unit of pressure equal to 10⁵ N/m using the current, or one of the historical, definitions of the SI units.

The bar appear in the International System of Units (SI), 1th ed. (1970) defined as "1 bar = 0,1 MPa = 10⁵ Pa" with the footnote "This unit and its symbol are included in Resolution 7 of the 9th C.G.P.M. (1948)."
(While the pascal appear in the 1st ed. as a symbol for N·s/m², it was adopted into SI at the 14th CGPM meeting in 1971.)

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "Units in use temporarily with the International Sytem."
The International System of Units (SI), 7th ed. (1998) changes the categorization to "Other non-SI units currently accepted for use with the International System."
The International System of Units (SI), 8th ed. (2006) changes the categorization to "Other non-SI units" and updates the footnote to: "The bar and its symbol are included in Resolution 7 of the 9th CGPM (1948; CR, 70). Since 1982 one bar has been used as the standard pressure for tabulating all thermodynamic data. Prior to 1982 the standard pressure used to be the standard atmosphere, equal to 1.013 25 bar, or 101 325 Pa."
The bar is omitted in the International System of Units (SI), 9th Edition (2019) (except appearing as an example in the context of typesetting of units).

The bar was implicitly redefined via the redefinition of the metre at the 17th CGPM meeting (1983), resolution 1.

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition in the International System of Units (SI), 9th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Bar_(unit))


**Formats:** [[JSON](bar.json)] [[MD](bar.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/bar",
    "title": "bar",
    "symbol": "bar",
    "display-symbol": "bar",
    "description": "A unit of pressure equal to 10\u2075 N/m using the current, or one of the historical, definitions of the SI units.\n\nThe bar appear in the International System of Units (SI), 1th ed. (1970) defined as \"1 bar = 0,1 MPa = 10\u2075 Pa\" with the footnote \"This unit and its symbol are included in Resolution 7 of the 9th C.G.P.M. (1948).\"\n(While the pascal appear in the 1st ed. as a symbol for N\u00b7s/m\u00b2, it was adopted into SI at the 14th CGPM meeting in 1971.)\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"Units in use temporarily with the International Sytem.\"\nThe International System of Units (SI), 7th ed. (1998) changes the categorization to \"Other non-SI units currently accepted for use with the International System.\"\nThe International System of Units (SI), 8th ed. (2006) changes the categorization to \"Other non-SI units\" and updates the footnote to: \"The bar and its symbol are included in Resolution 7 of the 9th CGPM (1948; CR, 70). Since 1982 one bar has been used as the standard pressure for tabulating all thermodynamic data. Prior to 1982 the standard pressure used to be the standard atmosphere, equal to 1.013 25 bar, or 101 325 Pa.\"\nThe bar is omitted in the International System of Units (SI), 9th Edition (2019) (except appearing as an example in the context of typesetting of units).\n\nThe bar was implicitly redefined via the redefinition of the metre at the 17th CGPM meeting (1983), resolution 1.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/bar",
        "https://schemas.optimade.org/units/v1.2.0/si/1983/temporary/bar"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "bar"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 9th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Bar_(unit)"
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
        "base-units-expression": "kg*m^-1*s^-2",
        "scale": {
            "exponent": 5
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "bar"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```