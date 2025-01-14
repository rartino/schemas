# femto, f (prefix)
This page documents an [OPTIMADE](https://www.optimade.org/) [Prefix Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/prefixes/femto`](https://schemas.optimade.org/units/v1.2.0/si/prefixes/femto)**  
**Definition name:** `femto`

**Prefix name:** femto  
**Latin symbol:** f  
**Display symbol:** f  
  
**Description:** The femto SI prefix defined as a dimensionless multiple of 10⁻¹⁵, defined at the 12:th CGPM Meeting in 1964, resolution 8.



**Resources:**

- [Definition in the 12th CGPM Meeting in 1964, resolution 8](https://www.bipm.org/en/committees/cg/cgpm/12-1964/resolution-8)
- [Wikipedia article describing SI prefixes](https://en.wikipedia.org/wiki/Metric_prefix)


**Formats:** [[JSON](femto.json)] [[MD](femto.md)]

**JSON definition:**

``` json
{
    "title": "femto",
    "symbol": "f",
    "display-symbol": "f",
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/prefixes/femto",
    "description": "The femto SI prefix defined as a dimensionless multiple of 10\u207b\u00b9\u2075, defined at the 12:th CGPM Meeting in 1964, resolution 8.",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "femto"
    },
    "resources": [
        {
            "relation": "Definition in the 12th CGPM Meeting in 1964, resolution 8",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/12-1964/resolution-8"
        },
        {
            "relation": "Wikipedia article describing SI prefixes",
            "resource-id": "https://en.wikipedia.org/wiki/Metric_prefix"
        }
    ],
    "defining-relation": {
        "base-units": [],
        "base-units-expression": "",
        "scale": {
            "exponent": -15
        }
    },
    "x-optimade-definition": {
        "kind": "prefix",
        "format": "1.2",
        "version": "1.2.0",
        "name": "femto"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```