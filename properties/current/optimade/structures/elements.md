# Elements (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements)**  
**Definition name:** `elements`

**Property name:** Elements  
**Description:** The chemical symbols of the different elements present in the structure.  
**Type:** list  

**Requirements/Conventions**:

- The strings are the chemical symbols, i.e., either a single uppercase letter or an uppercase letter followed by a number of lowercase letters.
- The order MUST be alphabetical.
- MUST refer to the same elements in the same order, and therefore be of the same length, as `elements_ratios`, if the latter is provided.
- Note: This property SHOULD NOT contain the string "X" to indicate non-chemical elements or "vacancy" to indicate vacancies (in contrast to the field `chemical_symbols` for the species property).

**Query examples**:

- A filter that matches all records of structures that contain Si, Al **and** O, and possibly other elements: `elements HAS ALL "Si", "Al", "O"`.
- To match structures with exactly these three elements, use `elements HAS ALL "Si", "Al", "O" AND elements LENGTH 3`.
- Note: length queries on this property can be equivalently formulated by filtering on the `nelements` property directly.

**Examples:**

- `['Al', 'Si', 'O']`
- `['He']`

**Formats:** [[JSON](elements.json)] [[MD](elements.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements",
    "title": "Elements",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "elements"
    },
    "type": [
        "array",
        "null"
    ],
    "description": "The chemical symbols of the different elements present in the structure.\n\n**Requirements/Conventions**:\n\n- The strings are the chemical symbols, i.e., either a single uppercase letter or an uppercase letter followed by a number of lowercase letters.\n- The order MUST be alphabetical.\n- MUST refer to the same elements in the same order, and therefore be of the same length, as `elements_ratios`, if the latter is provided.\n- Note: This property SHOULD NOT contain the string \"X\" to indicate non-chemical elements or \"vacancy\" to indicate vacancies (in contrast to the field `chemical_symbols` for the species property).\n\n**Query examples**:\n\n- A filter that matches all records of structures that contain Si, Al **and** O, and possibly other elements: `elements HAS ALL \"Si\", \"Al\", \"O\"`.\n- To match structures with exactly these three elements, use `elements HAS ALL \"Si\", \"Al\", \"O\" AND elements LENGTH 3`.\n- Note: length queries on this property can be equivalently formulated by filtering on the `nelements` property directly.",
    "examples": [
        [
            "Al",
            "Si",
            "O"
        ],
        [
            "He"
        ]
    ],
    "x-optimade-unit": "inapplicable",
    "items": {
        "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/common/element",
        "title": "Element",
        "x-optimade-type": "string",
        "x-optimade-definition": {
            "kind": "property",
            "version": "1.2.0",
            "format": "1.2",
            "name": "element"
        },
        "description": "The chemical symbol of an element\n\n**Requirements/Conventions:**\n\n- The strings are the chemical symbols, i.e., either a single uppercase letter or an uppercase letter followed by a number of lowercase letters.",
        "x-optimade-unit": "inapplicable",
        "type": [
            "string"
        ],
        "maxLength": 3,
        "enum": [
            "X",
            "H",
            "He",
            "Li",
            "Be",
            "B",
            "C",
            "N",
            "O",
            "F",
            "Ne",
            "Na",
            "Mg",
            "Al",
            "Si",
            "P",
            "S",
            "Cl",
            "Ar",
            "K",
            "Ca",
            "Sc",
            "Ti",
            "V",
            "Cr",
            "Mn",
            "Fe",
            "Co",
            "Ni",
            "Cu",
            "Zn",
            "Ga",
            "Ge",
            "As",
            "Se",
            "Br",
            "Kr",
            "Rb",
            "Sr",
            "Y",
            "Zr",
            "Nb",
            "Mo",
            "Tc",
            "Ru",
            "Rh",
            "Pd",
            "Ag",
            "Cd",
            "In",
            "Sn",
            "Sb",
            "Te",
            "I",
            "Xe",
            "Cs",
            "Ba",
            "La",
            "Ce",
            "Pr",
            "Nd",
            "Pm",
            "Sm",
            "Eu",
            "Gd",
            "Tb",
            "Dy",
            "Ho",
            "Er",
            "Tm",
            "Yb",
            "Lu",
            "Hf",
            "Ta",
            "W",
            "Re",
            "Os",
            "Ir",
            "Pt",
            "Au",
            "Hg",
            "Tl",
            "Pb",
            "Bi",
            "Po",
            "At",
            "Rn",
            "Fr",
            "Ra",
            "Ac",
            "Th",
            "Pa",
            "U",
            "Np",
            "Pu",
            "Am",
            "Cm",
            "Bk",
            "Cf",
            "Es",
            "Fm",
            "Md",
            "No",
            "Lr",
            "Rf",
            "Db",
            "Sg",
            "Bh",
            "Hs",
            "Mt",
            "Ds",
            "Rg",
            "Cn",
            "Uut",
            "Uuq",
            "Uup",
            "Uuh",
            "Uus",
            "Uuo",
            "Nh",
            "Fl",
            "Mc",
            "Lv",
            "Ts",
            "Og"
        ]
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```