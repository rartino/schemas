# Elements (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/common/element_list`](https://schemas.optimade.org/properties/v1.2.0/optimade/common/element_list)**  
**Definition name:** `element_list`

**Property name:** Elements  
**Description:** A list of elements.  
**Type:** list  



**Examples:**

- `['Si']`
- `['Al', 'O', 'Si']`

**Formats:** [[JSON](element_list.json)] [[MD](element_list.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/common/element_list",
    "title": "Elements",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "element_list"
    },
    "type": [
        "array"
    ],
    "description": "A list of elements.",
    "examples": [
        [
            "Si"
        ],
        [
            "Al",
            "O",
            "Si"
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