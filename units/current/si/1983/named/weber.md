# weber, Wb (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1983/named/weber`](https://schemas.optimade.org/units/v1.2.0/si/1983/named/weber)**  
**Definition name:** `weber`

**Unit name:** weber  
**Latin symbol:** weber  
**Display symbol:** Wb  
  
**Description:** A derived SI unit for magnetic flux equal to kg·m²·s⁻³·A⁻¹ in the 1983 SI units.

"The weber is the magnetic induction flux that, passing through a single-turn circuit, produces an electromotive force of one volt if it is reduced to zero in one second by uniform decay." [9th CGPM meeting in 1946]

The weber was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12, implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1, and again implicity redefined via the redefinition of the metre at the 17th CGPM meeting (1983), resolution 1.

**Resources:**

- [Definition at the 41st CIPM meeting (1946), resolution 2](https://www.bipm.org/en/committees/ci/cipm/41-1946/resolution-2)
- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Weber_(unit))


**Formats:** [[JSON](weber.json)] [[MD](weber.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1983/named/weber",
    "title": "weber",
    "symbol": "weber",
    "display-symbol": "Wb",
    "description": "A derived SI unit for magnetic flux equal to kg\u00b7m\u00b2\u00b7s\u207b\u00b3\u00b7A\u207b\u00b9 in the 1983 SI units.\n\n\"The weber is the magnetic induction flux that, passing through a single-turn circuit, produces an electromotive force of one volt if it is reduced to zero in one second by uniform decay.\" [9th CGPM meeting in 1946]\n\nThe weber was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12, implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1, and again implicity redefined via the redefinition of the metre at the 17th CGPM meeting (1983), resolution 1.",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "weber"
    },
    "resources": [
        {
            "relation": "Definition at the 41st CIPM meeting (1946), resolution 2",
            "resource-id": "https://www.bipm.org/en/committees/ci/cipm/41-1946/resolution-2"
        },
        {
            "relation": "Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1"
        },
        {
            "relation": "Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Weber_(unit)"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "A",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1983/base/ampere"
            },
            {
                "symbol": "kg",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1960/base/kilogram"
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
        "base-units-expression": "ampere^-1*kg*m^2*s^-3"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "weber"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```