# farad, F (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/2019/named/farad`](https://schemas.optimade.org/units/v1.2.0/si/2019/named/farad)**  
**Definition name:** `farad`

**Unit name:** farad  
**Latin symbol:** F  
**Display symbol:** F  
  
**Description:** A derived SI unit for electrical capacitance equal to kg⁻¹·m⁻²·s⁴·A² in the 2019 SI units.

"The farad is the capacitance of an electric capacitor between whose plates an electric potential difference of one volt appears when it is charged with an amount of electricity equal to one coulomb." [9th CGPM meeting in 1946]

The farad was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinitions of the second at the 13th CGPM Meeting in 1967, resolution 1, and the redefinitions of the ampere and kilogram at the 26th CGPM Meeting in 2018, resolution 1

**Resources:**

- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Redefinition of the kilogram and ampere in the 26th CGPM Meeting (2018), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Farad)


**Formats:** [[JSON](farad.json)] [[MD](farad.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/2019/named/farad",
    "title": "farad",
    "symbol": "F",
    "display-symbol": "F",
    "description": "A derived SI unit for electrical capacitance equal to kg\u207b\u00b9\u00b7m\u207b\u00b2\u00b7s\u2074\u00b7A\u00b2 in the 2019 SI units.\n\n\"The farad is the capacitance of an electric capacitor between whose plates an electric potential difference of one volt appears when it is charged with an amount of electricity equal to one coulomb.\" [9th CGPM meeting in 1946]\n\nThe farad was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinitions of the second at the 13th CGPM Meeting in 1967, resolution 1, and the redefinitions of the ampere and kilogram at the 26th CGPM Meeting in 2018, resolution 1",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "farad"
    },
    "resources": [
        {
            "relation": "Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1"
        },
        {
            "relation": "Redefinition of the kilogram and ampere in the 26th CGPM Meeting (2018), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Farad"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "A",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/2019/base/ampere"
            },
            {
                "symbol": "kg",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/2019/base/kilogram"
            },
            {
                "symbol": "m",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1983/base/metre"
            },
            {
                "symbol": "s",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1967/base/second"
            }
        ],
        "base-units-expression": "A^2*kg^-1*m^-2*s^4"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "farad"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```