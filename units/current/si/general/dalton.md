# dalton, Da (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/dalton`](https://schemas.optimade.org/units/v1.2.0/si/general/dalton)**  
**Definition name:** `dalton`

**Unit name:** dalton  
**Latin symbol:** Da  
**Display symbol:** Da  
  
**Description:** A unit of mass intended to represent a typical mass of a nucleon in an atom using the current, or one of the historical, definitions given in the editions of The International System of Units (SI).

The name dalton as an alternative name to *atomic mass unit* is defined in The International System of Units (SI), 7th ed. (1998) in a footnote to a table labeled "Non-SI units accepted for use with the International System, whose values in SI units are obtained experimentally" in the section "Units outside the international system".
The definition given is: "The unified atomic mass unit is equal to 1/12 of the mass of an unbound atom of the nuclide ¹²C, at rest, and in its ground state. In the field of biochemistry, the unified atomic mass unit is also called the dalton, symbol Da."

This definition makes the dalton equivalent to the atomic mass unit defined in The International System of Units (SI), 1st ed. (1970) (https://schemas.optimade.org/units/v1.2.0/si/general/atomicmassunit)

In the The International System of Units (SI) 8th ed. (2006) the definition is slightly adjusted, replacing "unbound" with "free": "The dalton (Da) and the unified atomic mass unit (u) are alternative names (and symbols) for the same unit, equal to 1/12 times the mass of a free carbon 12 atom, at rest and in its ground state."

All editions of The International System of Units (SI) note approximate relationships to the kilogram.
The 9th ed. states "1 Da = 1.660 539 066 60(50)×10⁻²⁷ kg", where the 2018 CODATA value has been used and the 2019 SI kilogram is referenced (https://schemas.optimade.org/units/v1.2.0/si/2019/base/kilogram).

Note: in the 2019 redefinition of the SI units, the dalton is the only unit listed as accepted for use with SI that does not have an exact relation to the base SI units.

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition in the International System of Units (SI), 9th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Dalton_(unit))
- [CODATA unified atomic mass unit fundamental physical constant: source for relationship to kg](https://physics.nist.gov/cgi-bin/cuu/Value?ukg)


**Formats:** [[JSON](dalton.json)] [[MD](dalton.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/dalton",
    "title": "dalton",
    "symbol": "Da",
    "display-symbol": "Da",
    "alternate-symbols": [
        "u"
    ],
    "description": "A unit of mass intended to represent a typical mass of a nucleon in an atom using the current, or one of the historical, definitions given in the editions of The International System of Units (SI).\n\nThe name dalton as an alternative name to *atomic mass unit* is defined in The International System of Units (SI), 7th ed. (1998) in a footnote to a table labeled \"Non-SI units accepted for use with the International System, whose values in SI units are obtained experimentally\" in the section \"Units outside the international system\".\nThe definition given is: \"The unified atomic mass unit is equal to 1/12 of the mass of an unbound atom of the nuclide \u00b9\u00b2C, at rest, and in its ground state. In the field of biochemistry, the unified atomic mass unit is also called the dalton, symbol Da.\"\n\nThis definition makes the dalton equivalent to the atomic mass unit defined in The International System of Units (SI), 1st ed. (1970) (https://schemas.optimade.org/units/v1.2.0/si/general/atomicmassunit)\n\nIn the The International System of Units (SI) 8th ed. (2006) the definition is slightly adjusted, replacing \"unbound\" with \"free\": \"The dalton (Da) and the unified atomic mass unit (u) are alternative names (and symbols) for the same unit, equal to 1/12 times the mass of a free carbon 12 atom, at rest and in its ground state.\"\n\nAll editions of The International System of Units (SI) note approximate relationships to the kilogram.\nThe 9th ed. states \"1 Da = 1.660 539 066 60(50)\u00d710\u207b\u00b2\u2077 kg\", where the 2018 CODATA value has been used and the 2019 SI kilogram is referenced (https://schemas.optimade.org/units/v1.2.0/si/2019/base/kilogram).\n\nNote: in the 2019 redefinition of the SI units, the dalton is the only unit listed as accepted for use with SI that does not have an exact relation to the base SI units.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/general/atomicmassunit"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "dalton"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 9th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Dalton_(unit)"
        },
        {
            "relation": "CODATA unified atomic mass unit fundamental physical constant: source for relationship to kg",
            "resource-id": "https://physics.nist.gov/cgi-bin/cuu/Value?ukg"
        }
    ],
    "approximate-relations": [
        {
            "base-units": [
                {
                    "symbol": "kg",
                    "id": "https://schema.optimade.org/units/v1.2.0/si/general/kilogram"
                }
            ],
            "base-units-expression": "kg",
            "scale": {
                "value": 1.6605390666e-27,
                "uncertainty": 5e-37
            }
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "dalton"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```