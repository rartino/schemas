# newton, N (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/newton`](https://schemas.optimade.org/units/v1.2.0/si/general/newton)**  
**Definition name:** `newton`

**Unit name:** newton  
**Latin symbol:** newton  
**Display symbol:** N  
  
**Description:** A unit for force and weight equal to kg·m·s⁻² using the current, or one of the historical, definitions of the SI units.

"The newton is the force that, in one second, imparts to a mass equal to one kilogram an increase in speed of one meter per second." [9th CGPM meeting in 1946]

The newton was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12, implicitly redefined via the redefinitions of the second at the 13th CGPM Meeting in 1967, resolution 1, the metre at the 17th CGPM meeting (1983), resolution 1, and the kilogram at the 26th CGPM Meeting (2018), resolution 1.

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Redefinition of the kilogram at the 26th CGPM Meeting (2018), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Newton_(unit))


**Formats:** [[JSON](newton.json)] [[MD](newton.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/newton",
    "title": "newton",
    "symbol": "newton",
    "display-symbol": "N",
    "description": "A unit for force and weight equal to kg\u00b7m\u00b7s\u207b\u00b2 using the current, or one of the historical, definitions of the SI units.\n\n\"The newton is the force that, in one second, imparts to a mass equal to one kilogram an increase in speed of one meter per second.\" [9th CGPM meeting in 1946]\n\nThe newton was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12, implicitly redefined via the redefinitions of the second at the 13th CGPM Meeting in 1967, resolution 1, the metre at the 17th CGPM meeting (1983), resolution 1, and the kilogram at the 26th CGPM Meeting (2018), resolution 1.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1960/named/newton",
        "https://schemas.optimade.org/units/v1.2.0/si/1967/named/newton",
        "https://schemas.optimade.org/units/v1.2.0/si/1983/named/newton",
        "https://schemas.optimade.org/units/v1.2.0/si/2019/named/newton"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "newton"
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
            "relation": "Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1"
        },
        {
            "relation": "Redefinition of the kilogram at the 26th CGPM Meeting (2018), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Newton_(unit)"
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
        "base-units-expression": "kg*m*s^-2"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "newton"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```