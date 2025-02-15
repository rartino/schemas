# ångström, Å (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/angstrom`](https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/angstrom)**  
**Definition name:** `angstrom`

**Unit name:** ångström  
**Latin symbol:** angstrom  
**Display symbol:** Å  
  
**Description:** A length equal to 10⁻¹⁰ meter, with meter defined according to the 1960 SI base units.

The ångström appear in the International System of Units (SI), 1th ed. (1970) defined as "1 Å = 0.1 nm = 10⁻¹⁰ m".

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "temporarily admitted" for use with the SI units.
The International System of Units (SI), 7th ed. (1998) changes the categorisation to "Other non-SI units currently accepted for use with the International System."
The International System of Units (SI), 8th ed. (2006) changes the categorization to "Other non-SI units" and adds as a clarifying footnote "The ångström is widely used by x-ray crystallographers and structural chemists because all chemical bonds lie in the range 1 to 3 ångströms. However it has no official sanction from the CIPM or the CGPM."
The ångström is omitted in the International System of Units (SI), 9th Edition (2019).

**Resources:**

- [Definition in the International System of Units (SI), 1th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Angstrom)


**Formats:** [[JSON](angstrom.json)] [[MD](angstrom.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/angstrom",
    "title": "\u00e5ngstr\u00f6m",
    "symbol": "angstrom",
    "display-symbol": "\u00c5",
    "description": "A length equal to 10\u207b\u00b9\u2070 meter, with meter defined according to the 1960 SI base units.\n\nThe \u00e5ngstr\u00f6m appear in the International System of Units (SI), 1th ed. (1970) defined as \"1 \u00c5 = 0.1 nm = 10\u207b\u00b9\u2070 m\".\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"temporarily admitted\" for use with the SI units.\nThe International System of Units (SI), 7th ed. (1998) changes the categorisation to \"Other non-SI units currently accepted for use with the International System.\"\nThe International System of Units (SI), 8th ed. (2006) changes the categorization to \"Other non-SI units\" and adds as a clarifying footnote \"The \u00e5ngstr\u00f6m is widely used by x-ray crystallographers and structural chemists because all chemical bonds lie in the range 1 to 3 \u00e5ngstr\u00f6ms. However it has no official sanction from the CIPM or the CGPM.\"\nThe \u00e5ngstr\u00f6m is omitted in the International System of Units (SI), 9th Edition (2019).",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "angstrom"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 1th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Angstrom"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "m",
                "id": "https://schema.optimade.org/units/v1.2.0/si/2019/base/metre"
            }
        ],
        "base-units-expression": "m",
        "scale": {
            "exponent": -10
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "angstrom"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```