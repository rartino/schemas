# Bohr magneton, \(mu_B\) (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/constants/v1.2.0/codata/2018/electromagnetic/bohrmagneton`](https://schemas.optimade.org/constants/v1.2.0/codata/2018/electromagnetic/bohrmagneton)**  
**Definition name:** `bohrmagneton`

**Unit name:** Bohr magneton  
**Latin symbol:** bohrmagneton  
**Display symbol:** \(mu_B\)  
  
**Description:** The 2018 CODATA Bohr magneton constant is defined as "1 mu_B = 9.274 010 0783(28)·10^-24 J·T^-1" with joule and tesla conforming to the 2019 redefinition of the SI derived units.



**Resources:**

- [2018 CODATA value Bohr magneton: source for relationship to joules*tesla^-1](https://physics.nist.gov/cgi-bin/cuu/Value?mub)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Bohr_magneton)


**Formats:** [[JSON](bohrmagneton.json)] [[MD](bohrmagneton.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/constants/v1.2.0/codata/2018/electromagnetic/bohrmagneton",
    "title": "Bohr magneton",
    "symbol": "bohrmagneton",
    "display-symbol": "\\(mu_B\\)",
    "description": "The 2018 CODATA Bohr magneton constant is defined as \"1 mu_B = 9.274 010 0783(28)\u00b710^-24 J\u00b7T^-1\" with joule and tesla conforming to the 2019 redefinition of the SI derived units.",
    "resources": [
        {
            "relation": "2018 CODATA value Bohr magneton: source for relationship to joules*tesla^-1",
            "resource-id": "https://physics.nist.gov/cgi-bin/cuu/Value?mub"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Bohr_magneton"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "J",
                "id": "https://schema.optimade.org/units/v1.2.0/si/2019/named/joule"
            },
            {
                "symbol": "T",
                "id": "https://schema.optimade.org/units/v1.2.0/si/2019/named/tesla"
            }
        ],
        "base-units-expression": "J*T^-1",
        "scale": {
            "numerator": 92740100783,
            "exponent": -34,
            "standard_uncertainty": 2.8e-34
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "bohrmagneton"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```