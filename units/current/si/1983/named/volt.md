# volt, V (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1983/named/volt`](https://schemas.optimade.org/units/v1.2.0/si/1983/named/volt)**  
**Definition name:** `volt`

**Unit name:** volt  
**Latin symbol:** volt  
**Display symbol:** V  
  
**Description:** A derived SI unit for electric potential, voltage, and electromotive force equal to kg·m²·s⁻³·A⁻¹ in the 1983 SI units.

"The volt is the electric potential difference that exists between two points of a conducting wire carrying a constant current of one ampere when the power dissipated between these points is equal to one watt." [9th CGPM meeting in 1946]

The volt was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1, and again redefined via the redefinition of the metre at the 17th CGPM Meeting in 1983, resolution 1.

**Resources:**

- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1)
- [Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1](https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Volt)


**Formats:** [[JSON](volt.json)] [[MD](volt.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1983/named/volt",
    "title": "volt",
    "symbol": "volt",
    "display-symbol": "V",
    "description": "A derived SI unit for electric potential, voltage, and electromotive force equal to kg\u00b7m\u00b2\u00b7s\u207b\u00b3\u00b7A\u207b\u00b9 in the 1983 SI units.\n\n\"The volt is the electric potential difference that exists between two points of a conducting wire carrying a constant current of one ampere when the power dissipated between these points is equal to one watt.\" [9th CGPM meeting in 1946]\n\nThe volt was defined at the 9th CGPM Meeting in 1946, included in SI at the 11th CGPM meeting in 1960, resolution 12 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1, and again redefined via the redefinition of the metre at the 17th CGPM Meeting in 1983, resolution 1.",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "V"
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
            "relation": "Redefinition of the second in the 13th CGPM Meeting (1967), resolution 1",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/13-1967/resolution-1"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Volt"
        }
    ],
    "defining-relation": {
        "base-units": [
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
            },
            {
                "symbol": "A",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1983/base/ampere"
            }
        ],
        "base-units-expression": "A^-1*kg*m^2*s^-3"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "volt"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```