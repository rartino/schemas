# candela, cd (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1983/base/cd`](https://schemas.optimade.org/units/v1.2.0/si/1983/base/cd)**  
**Definition name:** `candela`

**Unit name:** candela  
**Latin symbol:** cd  
**Display symbol:** cd  
  
**Description:** The candela is the SI base unit of luminous intensity in a given direction defined from the luminous intensity of monocromatic radiation at a specific frequency and radiant intensity at the 16th CGPM Meeting in 1979; implicitly redefined via the redefinition of the metre at the 17th CGPM Meeting in 1983.

"The candela is the luminous intensity, in a given direction, of a source that emits monochromatic radiation of frequency 540×10¹² hertz and that has a radiant intensity in that direction of 1/683 watt per steradian." [16th CGPM Meeting (1979), resolution 3].

Following the redefinition of the metre at the 17th CGPM Meeting in 1983, resolution 1, the implicitly redefined candela references:

- the SI 1967 derived hertz unit (https://schemas.optimade.org/units/v1.2.0/si/1967/named/hertz).
- the SI 1983 derived watt unit (https://schemas.optimade.org/units/v1.2.0/si/1983/named/watt).
- the SI 1960 supplementary unit steradian (https://schemas.optimade.org/units/v1.2.0/si/1960/supplementary/steradian).

**Resources:**

- [Definition at the 41st CIPM meeting (1946), resolution 2](https://www.bipm.org/en/committees/ci/cipm/41-1946/resolution-2)
- [Inclusion in SI at the establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Redefinition of the second at the 13th CGPM meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Candela)


**Formats:** [[JSON](cd.json)] [[MD](cd.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1983/base/cd",
    "title": "candela",
    "symbol": "cd",
    "display-symbol": "cd",
    "description": "The candela is the SI base unit of luminous intensity in a given direction defined from the luminous intensity of monocromatic radiation at a specific frequency and radiant intensity at the 16th CGPM Meeting in 1979; implicitly redefined via the redefinition of the metre at the 17th CGPM Meeting in 1983.\n\n\"The candela is the luminous intensity, in a given direction, of a source that emits monochromatic radiation of frequency 540\u00d710\u00b9\u00b2 hertz and that has a radiant intensity in that direction of 1/683 watt per steradian.\" [16th CGPM Meeting (1979), resolution 3].\n\nFollowing the redefinition of the metre at the 17th CGPM Meeting in 1983, resolution 1, the implicitly redefined candela references:\n\n- the SI 1967 derived hertz unit (https://schemas.optimade.org/units/v1.2.0/si/1967/named/hertz).\n- the SI 1983 derived watt unit (https://schemas.optimade.org/units/v1.2.0/si/1983/named/watt).\n- the SI 1960 supplementary unit steradian (https://schemas.optimade.org/units/v1.2.0/si/1960/supplementary/steradian).",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "cd"
    },
    "resources": [
        {
            "relation": "Definition at the 41st CIPM meeting (1946), resolution 2",
            "resource-id": "https://www.bipm.org/en/committees/ci/cipm/41-1946/resolution-2"
        },
        {
            "relation": "Inclusion in SI at the establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1"
        },
        {
            "relation": "Redefinition of the second at the 13th CGPM meeting (1967), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Candela"
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "candela"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```