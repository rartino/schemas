# henry, H (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/henry`](https://schemas.optimade.org/units/v1.2.0/si/general/henry)**  
**Definition name:** `henry`

**Unit name:** henry  
**Latin symbol:** H  
**Display symbol:** H  
  
**Description:** A unit for inductance equal to kg·m²·s⁻²·A⁻² using the current, or one of the historical, definitions of the SI units.

"The henry is the inductance of a closed circuit in which an electromotive force of one volt is produced when the electric current passing through the circuit varies uniformly at a rate of one ampere per second." [9th CGPM meeting in 1946]

The henry was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12, and implicitly redefined via the redefinitions of the second at the 13th CGPM Meeting in 1967, resolution 1, the metre at the 17th CGPM meeting (1983), resolution 1, and the kilogram and ampere at the 26th CGPM Meeting (2018), resolution 1.

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Redefinition of the second at the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Redefinition of the kilogram and ampere at the 26th CGPM Meeting (2018), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Henry_(unit))


**Formats:** [[JSON](henry.json)] [[MD](henry.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/henry",
    "title": "henry",
    "symbol": "H",
    "display-symbol": "H",
    "description": "A unit for inductance equal to kg\u00b7m\u00b2\u00b7s\u207b\u00b2\u00b7A\u207b\u00b2 using the current, or one of the historical, definitions of the SI units.\n\n\"The henry is the inductance of a closed circuit in which an electromotive force of one volt is produced when the electric current passing through the circuit varies uniformly at a rate of one ampere per second.\" [9th CGPM meeting in 1946]\n\nThe henry was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12, and implicitly redefined via the redefinitions of the second at the 13th CGPM Meeting in 1967, resolution 1, the metre at the 17th CGPM meeting (1983), resolution 1, and the kilogram and ampere at the 26th CGPM Meeting (2018), resolution 1.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1960/named/henry",
        "https://schemas.optimade.org/units/v1.2.0/si/1967/named/henry",
        "https://schemas.optimade.org/units/v1.2.0/si/1983/named/henry",
        "https://schemas.optimade.org/units/v1.2.0/si/2019/named/henry"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "henry"
    },
    "resources": [
        {
            "relation": "Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1"
        },
        {
            "relation": "Redefinition of the second at the 13th CGPM Meeting (1967), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1"
        },
        {
            "relation": "Redefinition of the kilogram and ampere at the 26th CGPM Meeting (2018), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/26-2018/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Henry_(unit)"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "A",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/general/ampere"
            },
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
        "base-units-expression": "A^-2*kg*m^2*s^-2"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "henry"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```