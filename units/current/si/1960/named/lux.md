# lux, lx (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1960/named/lux`](https://schemas.optimade.org/units/v1.2.0/si/1960/named/lux)**  
**Definition name:** `lux`

**Unit name:** lux  
**Latin symbol:** lx  
**Display symbol:** lx  
  
**Description:** A derived SI unit for illuminance equal to cd⋅sr⋅m⁻² in the 1960 SI base units.

"The lux is the illuminance of a surface that receives a uniformly distributed luminous flux of one lumen per square meter." [9th CGPM meeting in 1946]

**Resources:**

- [Definition at the 9st CGPM meeting (1948)](https://www.bipm.org/en/committees/cg/cgpm/9-1948)
- [Definition and establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Lux)


**Formats:** [[JSON](lux.json)] [[MD](lux.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1960/named/lux",
    "title": "lux",
    "symbol": "lx",
    "display-symbol": "lx",
    "description": "A derived SI unit for illuminance equal to cd\u22c5sr\u22c5m\u207b\u00b2 in the 1960 SI base units.\n\n\"The lux is the illuminance of a surface that receives a uniformly distributed luminous flux of one lumen per square meter.\" [9th CGPM meeting in 1946]",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "lux"
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
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Lux"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "cd",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1960/base/candela"
            },
            {
                "symbol": "sr",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1960/named/steradian"
            },
            {
                "symbol": "m",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre"
            }
        ],
        "base-units-expression": "cd*m^-2*sr"
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "lux"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```