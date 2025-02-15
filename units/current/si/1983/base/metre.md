# metre, m (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1983/base/metre`](https://schemas.optimade.org/units/v1.2.0/si/1983/base/metre)**  
**Definition name:** `metre`

**Unit name:** metre  
**Latin symbol:** m  
**Display symbol:** m  
  
**Description:** The metre, or meter, is the SI base unit of length defined via the distance light travels in vaccum during a fixed time interval after the redefinition at the 17th CGPM Meeting in 1983.

"The metre is the length of the path travelled by light in vacuum during a time interval of 1/299792458 of a second." [17th CGPM Meeting (1983), resolution 1].

At the 26th CGPM Meeting (2018), resolution 1 the definition was rephrased to: "The metre, symbol m, is the SI unit of length. It is defined by taking the fixed numerical value of the speed of light in vacuum \(c\) to be 299792458 when expressed in the unit m⋅s⁻¹, where the second is defined in terms of the caesium frequency \(\Delta \nu_\textrm{Cs}\)."

This definition references the SI 1967 second (https://schemas.optimade.org/units/v1.2.0/si/1967/base/second).

**Resources:**

- [Definition at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Metre)


**Formats:** [[JSON](metre.json)] [[MD](metre.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1983/base/metre",
    "title": "metre",
    "symbol": "m",
    "display-symbol": "m",
    "alternate-symbols": [
        "metre",
        "meter"
    ],
    "description": "The metre, or meter, is the SI base unit of length defined via the distance light travels in vaccum during a fixed time interval after the redefinition at the 17th CGPM Meeting in 1983.\n\n\"The metre is the length of the path travelled by light in vacuum during a time interval of 1/299792458 of a second.\" [17th CGPM Meeting (1983), resolution 1].\n\nAt the 26th CGPM Meeting (2018), resolution 1 the definition was rephrased to: \"The metre, symbol m, is the SI unit of length. It is defined by taking the fixed numerical value of the speed of light in vacuum \\(c\\) to be 299792458 when expressed in the unit m\u22c5s\u207b\u00b9, where the second is defined in terms of the caesium frequency \\(\\Delta \\nu_\\textrm{Cs}\\).\"\n\nThis definition references the SI 1967 second (https://schemas.optimade.org/units/v1.2.0/si/1967/base/second).",
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