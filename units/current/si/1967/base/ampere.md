# ampere, A (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1967/base/ampere`](https://schemas.optimade.org/units/v1.2.0/si/1967/base/ampere)**  
**Definition name:** `ampere`

**Unit name:** ampere  
**Latin symbol:** A  
**Display symbol:** A  
  
**Description:** The SI base unit of electric current defined from the force between parallel wires carrying an electric current at the 41st CIPM meeting (1946), resolution 2 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1.

"The ampere is that constant current which, if maintained in two straight parallel conductors of infinite length, of negligible circular cross-section, and placed 1 metre apart in vacuum, would produce between these conductors a force equal to 2×10⁻⁷ MKS unit of force per metre of length." [41st CIPM meeting (1946), Resolution 2].

Furthermore, following the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1, the implicitly redefined ampere references:

- the metre in the definition references the SI 1960 metre (https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre)
- the MKS unit of force references the derived newton unit (https://schemas.optimade.org/units/v1.2.0/si/1960/derived/newton) equal to kilogram·metre·second⁻², referencing the SI 1960 kilogram (https://schemas.optimade.org/units/v1.2.0/si/1960/base/kilogram) and metre (https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre); and the 1967 definition of the second (https://schemas.optimade.org/units/v1.2.0/si/1967/base/second).

**Resources:**

- [Definition at the 41st CIPM meeting (1946), resolution 2](https://www.bipm.org/en/committees/ci/cipm/41-1946/resolution-2)
- [Establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.](https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Ampere)


**Formats:** [[JSON](ampere.json)] [[MD](ampere.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1967/base/ampere",
    "title": "ampere",
    "symbol": "A",
    "display-symbol": "A",
    "description": "The SI base unit of electric current defined from the force between parallel wires carrying an electric current at the 41st CIPM meeting (1946), resolution 2 and implicitly redefined via the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1.\n\n\"The ampere is that constant current which, if maintained in two straight parallel conductors of infinite length, of negligible circular cross-section, and placed 1 metre apart in vacuum, would produce between these conductors a force equal to 2\u00d710\u207b\u2077 MKS unit of force per metre of length.\" [41st CIPM meeting (1946), Resolution 2].\n\nFurthermore, following the redefinition of the second at the 13th CGPM Meeting in 1967, resolution 1, the implicitly redefined ampere references:\n\n- the metre in the definition references the SI 1960 metre (https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre)\n- the MKS unit of force references the derived newton unit (https://schemas.optimade.org/units/v1.2.0/si/1960/derived/newton) equal to kilogram\u00b7metre\u00b7second\u207b\u00b2, referencing the SI 1960 kilogram (https://schemas.optimade.org/units/v1.2.0/si/1960/base/kilogram) and metre (https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre); and the 1967 definition of the second (https://schemas.optimade.org/units/v1.2.0/si/1967/base/second).",
    "resources": [
        {
            "relation": "Definition at the 41st CIPM meeting (1946), resolution 2",
            "resource-id": "https://www.bipm.org/en/committees/ci/cipm/41-1946/resolution-2"
        },
        {
            "relation": "Establishment of the SI unit system at the 11th CGPM meeting (1960), resolution 12.",
            "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/11-1960/resolution-12"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Ampere"
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "ampere"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```