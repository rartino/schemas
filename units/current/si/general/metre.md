# metre, m (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/general/metre`](https://schemas.optimade.org/units/v1.2.0/si/general/metre)**  
**Definition name:** `metre`

**Unit name:** metre  
**Latin symbol:** m  
**Display symbol:** m  
  
**Description:** The metre, or meter, is a unit of length using the current, or one of the historical, definitions of the SI units.

The current definition in its most recent phrasing at the 26th CGPM Meeting in 2018, resolution 1 is: "The metre, symbol m, is the SI unit of length. It is defined by taking the fixed numerical value of the speed of light in vacuum \(c\) to be 299792458 when expressed in the unit m⋅s⁻¹, where the second is defined in terms of the caesium frequency \(\Delta \nu_\textrm{Cs}\)."

This is a rephrasing of a definition at the 17th CGPM Meeting (1983), resolution 1: "The metre is the length of the path travelled by light in vacuum during a time interval of 1/299792458 of a second." [17th CGPM Meeting (1983), resolution 1].

The prior definition at the 11th CGPM meeting (1960), resolution 6 was: "The metre is the length equal to 1650763.73 wavelengths in vacuum of the radiation corresponding to the transition between the levels 2p₁₀ and 5d₅ of the krypton 86 atom."

This is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.
This definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.

**Resources:**

- [Definition at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Definition at the 11th CGPM meeting (1960), resolution 6.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-6)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Metre)


**Formats:** [[JSON](metre.json)] [[MD](metre.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/metre",
    "title": "metre",
    "symbol": "m",
    "display-symbol": "m",
    "alternate-symbols": [
        "metre",
        "meter"
    ],
    "description": "The metre, or meter, is a unit of length using the current, or one of the historical, definitions of the SI units.\n\nThe current definition in its most recent phrasing at the 26th CGPM Meeting in 2018, resolution 1 is: \"The metre, symbol m, is the SI unit of length. It is defined by taking the fixed numerical value of the speed of light in vacuum \\(c\\) to be 299792458 when expressed in the unit m\u22c5s\u207b\u00b9, where the second is defined in terms of the caesium frequency \\(\\Delta \\nu_\\textrm{Cs}\\).\"\n\nThis is a rephrasing of a definition at the 17th CGPM Meeting (1983), resolution 1: \"The metre is the length of the path travelled by light in vacuum during a time interval of 1/299792458 of a second.\" [17th CGPM Meeting (1983), resolution 1].\n\nThe prior definition at the 11th CGPM meeting (1960), resolution 6 was: \"The metre is the length equal to 1650763.73 wavelengths in vacuum of the radiation corresponding to the transition between the levels 2p\u2081\u2080 and 5d\u2085 of the krypton 86 atom.\"\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
    "compatibility": [
        "https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre",
        "https://schemas.optimade.org/units/v1.2.0/si/1983/base/metre"
    ],
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "metre"
    },
    "resources": [
        {
            "relation": "Definition at the 17th CGPM meeting (1983), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1"
        },
        {
            "relation": "Definition at the 11th CGPM meeting (1960), resolution 6.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-6"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Metre"
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "metre"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```