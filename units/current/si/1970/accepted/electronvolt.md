# electron volt, eV (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/electronvolt`](https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/electronvolt)**  
**Definition name:** `electronvolt`

**Unit name:** electron volt  
**Latin symbol:** eV  
**Display symbol:** eV  
  
**Description:** A unit of energy equal to the amount of kinetic energy acquired by an electron as it accelerates through a 1 volt potential difference in a vacuum using the 1967 SI units.

The electronvolt appear in the International System of Units (SI), 1th ed. (1970) defined as "1 electronvolt is the energy acquired by an electron after traversing a potential difference of 1 V in a vacuum; 1 eV = 1.60219×10⁻¹⁹ J approximately."
The definition makes the unit equal to 1 volt times the experimentally determined value of the elementary charge.
Later editions update the approximate relation to use the respectively recommended value by CODATA at the time.

In the 1970 definition, the volt refers to the 1967 volt derived named SI unit (https://schema.optimade.org/units/v1.2.0/si/1967/named/volt).

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "units for use with the SI in specific domains."
The International System of Units (SI), 2th ed. (1973) categorizes the unit as "Non-SI units accepted for use with the International System, whose values in SI units are obtained experimentally."
Following the redefinitions of the SI units 2019, the electronvolt has an exact relationship to the joule, hence the International System of Units (SI), 9th ed. (2019) notes "1 eV = 1.602176634·10⁻¹⁹ J" and categorizes the unit as "Non-SI units accepted for use with the SI units".
The footnote is also rephrased to say: "The electron volt is the kinetic energy acquired by an electron after traversing a potential difference of 1 V in a vacuum. The electronvolt is often combined with the SI prefixes."

**Resources:**

- [Definition in the International System of Units (SI), 9th Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Electronvolt)


**Formats:** [[JSON](electronvolt.json)] [[MD](electronvolt.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/electronvolt",
    "title": "electron volt",
    "symbol": "eV",
    "display-symbol": "eV",
    "description": "A unit of energy equal to the amount of kinetic energy acquired by an electron as it accelerates through a 1 volt potential difference in a vacuum using the 1967 SI units.\n\nThe electronvolt appear in the International System of Units (SI), 1th ed. (1970) defined as \"1 electronvolt is the energy acquired by an electron after traversing a potential difference of 1 V in a vacuum; 1 eV = 1.60219\u00d710\u207b\u00b9\u2079 J approximately.\"\nThe definition makes the unit equal to 1 volt times the experimentally determined value of the elementary charge.\nLater editions update the approximate relation to use the respectively recommended value by CODATA at the time.\n\nIn the 1970 definition, the volt refers to the 1967 volt derived named SI unit (https://schema.optimade.org/units/v1.2.0/si/1967/named/volt).\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"units for use with the SI in specific domains.\"\nThe International System of Units (SI), 2th ed. (1973) categorizes the unit as \"Non-SI units accepted for use with the International System, whose values in SI units are obtained experimentally.\"\nFollowing the redefinitions of the SI units 2019, the electronvolt has an exact relationship to the joule, hence the International System of Units (SI), 9th ed. (2019) notes \"1 eV = 1.602176634\u00b710\u207b\u00b9\u2079 J\" and categorizes the unit as \"Non-SI units accepted for use with the SI units\".\nThe footnote is also rephrased to say: \"The electron volt is the kinetic energy acquired by an electron after traversing a potential difference of 1 V in a vacuum. The electronvolt is often combined with the SI prefixes.\"",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "angstrom"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 9th Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Electronvolt"
        }
    ],
    "approximate-relations": [
        {
            "base-units": [
                {
                    "symbol": "V",
                    "id": "https://schema.optimade.org/units/v1.2.0/si/1967/named/volt"
                },
                {
                    "symbol": "e",
                    "id": "https://schema.optimade.org/constants/v1.2.0/codata/2018/electromagnetic/elementarycharge"
                }
            ],
            "base-units-expression": "e*V"
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "electronvolt"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```