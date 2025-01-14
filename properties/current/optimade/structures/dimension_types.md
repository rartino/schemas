# Dimension types (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/dimension_types`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/dimension_types)**  
**Definition name:** `dimension_types`

**Property name:** Dimension types  
**Description:** List of three integers describing the periodicity of the boundaries of the unit cell. For each direction indicated by the three lattice_vectors, this list indicates if the direction is periodic (value 1) or non-periodic (value 0). Note: the elements in this list each refer to the direction of the corresponding entry in lattice_vectors and not the Cartesian x, y, z directions.  
**Type:** list  

**Requirements/Conventions**:

- MUST be a list of length 3.
- Each integer element MUST assume only the value 0 or 1.

**Explained examples**:

- A nonperiodic structure, for example, for a single molecule : `[0, 0, 0]`
- A unit cell that is periodic in the direction of the third lattice vector, for example for a carbon nanotube: `[0, 0, 1]`
- For a 2D surface/slab, with a unit cell that is periodic in the direction of the first and third lattice vectors: `[1, 0, 1]`
- For a bulk 3D system with a unit cell that is periodic in all directions: `[1, 1, 1]`

**Examples:**

- `[0, 0, 0]`
- `[0, 0, 1]`
- `[1, 0, 1]`

**Formats:** [[JSON](dimension_types.json)] [[MD](dimension_types.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/dimension_types",
    "title": "Dimension types",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "dimension_types"
    },
    "type": [
        "array",
        "null"
    ],
    "description": "List of three integers describing the periodicity of the boundaries of the unit cell. For each direction indicated by the three lattice_vectors, this list indicates if the direction is periodic (value 1) or non-periodic (value 0). Note: the elements in this list each refer to the direction of the corresponding entry in lattice_vectors and not the Cartesian x, y, z directions.\n\n**Requirements/Conventions**:\n\n- MUST be a list of length 3.\n- Each integer element MUST assume only the value 0 or 1.\n\n**Explained examples**:\n\n- A nonperiodic structure, for example, for a single molecule : `[0, 0, 0]`\n- A unit cell that is periodic in the direction of the third lattice vector, for example for a carbon nanotube: `[0, 0, 1]`\n- For a 2D surface/slab, with a unit cell that is periodic in the direction of the first and third lattice vectors: `[1, 0, 1]`\n- For a bulk 3D system with a unit cell that is periodic in all directions: `[1, 1, 1]`",
    "examples": [
        [
            0,
            0,
            0
        ],
        [
            0,
            0,
            1
        ],
        [
            1,
            0,
            1
        ]
    ],
    "x-optimade-unit": "inapplicable",
    "items": {
        "x-optimade-type": "integer",
        "type": [
            "integer"
        ],
        "x-optimade-unit": "inapplicable",
        "description": "The integers 0 and 1 are used to mean false/true in a boolean flag indicating a periodic direction.",
        "enum": [
            0,
            1
        ]
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```