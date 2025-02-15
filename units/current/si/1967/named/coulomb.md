# coulomb, C (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1967/named/coulomb`](https://schemas.optimade.org/units/v1.2.0/si/1967/named/coulomb)**  
**Definition name:** `coulomb`

**Unit name:** coulomb  
**Latin symbol:** coulomb  
**Display symbol:** C  
  
**Description:** A derived SI unit for electric charge equal to s·A in the 1967 SI base units.

"The coulomb is the amount of electricity transported in one second by a current of one ampere." [9th CGPM meeting in 1946]

The coulomb was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1.

**Resources:**

- [Definition at the 9st CGPM meeting (1948)](https://www.bipm.org/en/committees/cg/cgpm/9-1948)
- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Coulomb)


**Formats:** [[JSON](coulomb.json)] [[MD](coulomb.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1967/named/coulomb",
    "title": "coulomb",
    "symbol": "coulomb",
    "display-symbol": "C",
    "description": "A derived SI unit for electric charge equal to s\u00b7A in the 1967 SI base units.\n\n\"The coulomb is the amount of electricity transported in one second by a current of one ampere.\" [9th CGPM meeting in 1946]\n\nThe coulomb was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1.",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "coulomb"
    },
    "resources": [
        {
            "relation": "Definition at the 9st CGPM meeting (1948)",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/9-1948"
        },
        {
            "relation": "Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Coulomb"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "s",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1967/base/second"
            },
            {
                "symbol": "A",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1967/base/ampere"
            }
        ],
        "base-units-expression": "A*s"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "coulomb"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```