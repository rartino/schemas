# hertz, Hz (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/hertz`](https://schemas.optimade.org/units/v1.2.0/si/general/hertz)**  
**Definition name:** `hertz`

**Unit name:** hertz  
**Latin symbol:** hertz  
**Display symbol:** Hz  
  
**Description:** A unit for frequency equal to s⁻¹ using the current, or one of the historical, definitions of the SI units.

"The frequency of a periodic phenomenon is expressed in hertz, as the inverse of its period expressed in seconds." [9th CGPM meeting in 1946]

The hertz was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1.

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition at the 9st CGPM meeting (1948)](https://www.bipm.org/en/committees/cg/cgpm/9-1948)
- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Hertz)


**Formats:** [[JSON](hertz.json)] [[MD](hertz.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/hertz",
    "title": "hertz",
    "symbol": "hertz",
    "display-symbol": "Hz",
    "description": "A unit for frequency equal to s\u207b\u00b9 using the current, or one of the historical, definitions of the SI units.\n\n\"The frequency of a periodic phenomenon is expressed in hertz, as the inverse of its period expressed in seconds.\" [9th CGPM meeting in 1946]\n\nThe hertz was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1960/named/hertz",
        "https://schemas.optimade.org/units/v1.2.0/si/1967/named/hertz"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "hertz"
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
            "resource-id": "https://en.wikipedia.org/wiki/Hertz"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "s",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/general/second"
            }
        ],
        "base-units-expression": "s^-1"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "hertz"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```