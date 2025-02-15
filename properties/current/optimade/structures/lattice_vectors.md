# Lattice vectors (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/lattice_vectors`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/lattice_vectors)**  
**Definition name:** `lattice_vectors`

**Property name:** Lattice vectors  
**Description:** The three lattice vectors in Cartesian coordinates, in ångström (Å).  
**Type:** list  

**Requirements/Conventions**:

- MUST be a list of three vectors *a*, *b*, and *c*, where each of the vectors MUST BE a list of the vector's coordinates along the x, y, and z Cartesian coordinates.
  (Therefore, the first index runs over the three lattice vectors and the second index runs over the x, y, z Cartesian coordinates).
- For databases that do not define an absolute Cartesian system (e.g., only defining the length and angles between vectors), the first lattice vector SHOULD be set along *x* and the second on the *xy*-plane.
- MUST always contain three vectors of three coordinates each, independently of the elements of property `dimension_types`.
  The vectors SHOULD by convention be chosen so the determinant of the `lattice_vectors` matrix is different from zero.
  The vectors in the non-periodic directions have no significance beyond fulfilling these requirements.
- The coordinates of the lattice vectors of non-periodic dimensions (i.e., those dimensions for which `dimension_types` is `0`) MAY be given as a list of all `null` values.
  If a lattice vector contains the value `null`, all coordinates of that lattice vector MUST be `null`.

**Explained examples**:

- `[[4.0,0.0,0.0],[0.0,4.0,0.0],[0.0,1.0,4.0]]` represents a cell, where the first vector is (4, 0, 0), i.e., a vector aligned along the x axis of length 4 Å; the second vector is (0, 4, 0); and the third vector is (0, 1, 4).

**Examples:**

- `[[4.0, 0.0, 0.0], [0.0, 4.0, 0.0], [0.0, 1.0, 4.0]]`

**Formats:** [[JSON](lattice_vectors.json)] [[MD](lattice_vectors.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/lattice_vectors",
    "title": "Lattice vectors",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "lattice_vectors"
    },
    "x-optimade-unit-definitions": [
        {
            "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/angstrom",
            "title": "\u00e5ngstr\u00f6m",
            "symbol": "angstrom",
            "display-symbol": "\u00c5",
            "description": "A unit of length equal to 10\u207b\u00b9\u2070 meter, using the current, or one of the historical, definitions of the SI units.\n\nThe \u00e5ngstr\u00f6m appear in the International System of Units (SI), 1th ed. (1970) defined as \"1 \u00c5 = 0.1 nm = 10\u207b\u00b9\u2070 m\".\n\nThe \u00e5ngstr\u00f6m was implicitly redefined via the redefinition of the metre at the 17th CGPM meeting (1983), resolution 1.\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"temporarily admitted\" for use with the SI units.\nThe International System of Units (SI), 7th ed. (1998) changes the categorisation to \"Other non-SI units currently accepted for use with the International System.\"\nThe International System of Units (SI), 8th ed. (2006) changes the categorization to \"Other non-SI units\" and adds as a clarifying footnote \"The \u00e5ngstr\u00f6m is widely used by x-ray crystallographers and structural chemists because all chemical bonds lie in the range 1 to 3 \u00e5ngstr\u00f6ms. However it has no official sanction from the CIPM or the CGPM.\"\nThe \u00e5ngstr\u00f6m is omitted in the International System of Units (SI), 9th Edition (2019).\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
            "compatibility": [
                "https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/angstrom",
                "https://schemas.optimade.org/units/v1.2.0/si/1983/temporary/angstrom"
            ],
            "standard": {
                "name": "gnu units",
                "version": "3.15",
                "symbol": "angstrom"
            },
            "resources": [
                {
                    "relation": "Definition in the International System of Units (SI), 1th Edition",
                    "resource-id": "https://www.bipm.org/en/publications/si-brochure"
                },
                {
                    "relation": "Redefinition of the metre at the 17th CGPM meeting (1983), resolution 1",
                    "resource-id": "https://www.bipm.org/en/committees/cg/cgpm/17-1983/resolution-1"
                },
                {
                    "relation": "Wikipedia article describing the unit",
                    "resource-id": "https://en.wikipedia.org/wiki/Angstrom"
                }
            ],
            "defining-relation": {
                "base-units": [
                    {
                        "symbol": "m",
                        "id": "https://schema.optimade.org/units/v1.2.0/si/general/metre"
                    }
                ],
                "base-units-expression": "m",
                "scale": {
                    "exponent": -10
                }
            },
            "x-optimade-definition": {
                "kind": "unit",
                "format": "1.2",
                "version": "1.2.0",
                "name": "angstrom"
            }
        }
    ],
    "type": [
        "array",
        "null"
    ],
    "description": "The three lattice vectors in Cartesian coordinates, in \u00e5ngstr\u00f6m (\u00c5).\n\n**Requirements/Conventions**:\n\n- MUST be a list of three vectors *a*, *b*, and *c*, where each of the vectors MUST BE a list of the vector's coordinates along the x, y, and z Cartesian coordinates.\n  (Therefore, the first index runs over the three lattice vectors and the second index runs over the x, y, z Cartesian coordinates).\n- For databases that do not define an absolute Cartesian system (e.g., only defining the length and angles between vectors), the first lattice vector SHOULD be set along *x* and the second on the *xy*-plane.\n- MUST always contain three vectors of three coordinates each, independently of the elements of property `dimension_types`.\n  The vectors SHOULD by convention be chosen so the determinant of the `lattice_vectors` matrix is different from zero.\n  The vectors in the non-periodic directions have no significance beyond fulfilling these requirements.\n- The coordinates of the lattice vectors of non-periodic dimensions (i.e., those dimensions for which `dimension_types` is `0`) MAY be given as a list of all `null` values.\n  If a lattice vector contains the value `null`, all coordinates of that lattice vector MUST be `null`.\n\n**Explained examples**:\n\n- `[[4.0,0.0,0.0],[0.0,4.0,0.0],[0.0,1.0,4.0]]` represents a cell, where the first vector is (4, 0, 0), i.e., a vector aligned along the x axis of length 4 \u00c5; the second vector is (0, 4, 0); and the third vector is (0, 1, 4).",
    "examples": [
        [
            [
                4.0,
                0.0,
                0.0
            ],
            [
                0.0,
                4.0,
                0.0
            ],
            [
                0.0,
                1.0,
                4.0
            ]
        ]
    ],
    "x-optimade-unit": "inapplicable",
    "items": {
        "x-optimade-type": "list",
        "type": [
            "array"
        ],
        "x-optimade-unit": "inapplicable",
        "items": {
            "x-optimade-type": "float",
            "type": [
                "number"
            ],
            "x-optimade-unit": "angstrom"
        }
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```