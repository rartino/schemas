# Assemblies (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/assemblies`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/assemblies)**  
**Definition name:** `assembiles`

**Property name:** Assemblies  
**Description:** A description of groups of sites that are statistically correlated.  
**Type:** dictionary  

**Requirements/Conventions**:

- The property SHOULD be `null` for entries that have no partial occupancies.
- If present, the correct flag MUST be set in the list `structure_features` (see property `structure_features`).
- Client implementations MUST check its presence (as its presence changes the interpretation of the structure).
- If present, it MUST be a list of dictionaries, each of which represents an assembly and MUST have the following two keys:

  - **sites_in_groups**: Index of the sites (0-based) that belong to each group for each assembly.

    Example: `[[1], [2]]`: two groups, one with the second site, one with the third.
    Example: `[[1,2], [3]]`: one group with the second and third site, one with the fourth.

  - **group_probabilities**: Statistical probability of each group. It MUST have the same length as `sites_in_groups`.
    It SHOULD sum to one.
    See below for examples of how to specify the probability of the occurrence of a vacancy.
    The possible reasons for the values not to sum to one are the same as already specified above for the `concentration` of each `species`, see property `species`.

- If a site is not present in any group, it means that it is present with 100 % probability (as if no assembly was specified).
- A site MUST NOT appear in more than one group.

**Explained examples**:

- `{"sites_in_groups": [[0], [1]], "group_probabilities": [0.3, 0.7]}`: the first site and the second site never occur at the same time in the unit cell.
  Statistically, 30 % of the times the first site is present, while 70 % of the times the second site is present.
- `{"sites_in_groups": [[1,2], [3]], "group_probabilities": [0.3, 0.7]}`: the second and third sites are either present together or not present; they form the first group of atoms for this assembly.
  The second group is formed by the fourth site.
  Sites of the first group (the second and the third) are never present at the same time as the fourth site.
  30 % of times sites 1 and 2 are present (and site 3 is absent); 70 % of times site 3 is present (and sites 1 and 2 are absent).

- **Notes**:

  - Assemblies are essential to represent, for instance, the situation where an atom can statistically occupy two different positions (sites).
  - By defining groups, it is possible to represent, e.g., the case where a functional molecule (and not just one atom) is either present or absent (or the case where it is present in two conformations).
  - Considerations on virtual alloys and on vacancies: In the special case of a virtual alloy, these specifications allow two different, equivalent ways of specifying them.
    For instance, for a site at the origin with 30 % probability of being occupied by Si, 50 % probability of being occupied by Ge, and 20 % of being a vacancy, the following two representations are possible:

    - Using a single species:

      ```

           {
             "cartesian_site_positions": [[0,0,0]],
             "species_at_sites": ["SiGe-vac"],
             "species": [
               {
                 "name": "SiGe-vac",
                 "chemical_symbols": ["Si", "Ge", "vacancy"],
                 "concentration": [0.3, 0.5, 0.2]
               }
             ]
             // ...
           }
      ```


    - Using multiple species and the assemblies:

      ```

           {
             "cartesian_site_positions": [ [0,0,0], [0,0,0], [0,0,0] ],
             "species_at_sites": ["Si", "Ge", "vac"],
             "species": [
               { "name": "Si", "chemical_symbols": ["Si"], "concentration": [1.0] },
               { "name": "Ge", "chemical_symbols": ["Ge"], "concentration": [1.0] },
               { "name": "vac", "chemical_symbols": ["vacancy"], "concentration": [1.0] }
             ],
             "assemblies": [
               {
                 "sites_in_groups": [ [0], [1], [2] ],
                 "group_probabilities": [0.3, 0.5, 0.2]
               }
             ]
             // ...
           }
      ```

  - It is up to the database provider to decide which representation to use, typically depending on the internal format in which the structure is stored.
    However, given a structure identified by a unique ID, the API implementation MUST always provide the same representation for it.
  - The probabilities of occurrence of different assemblies are uncorrelated.
    So, for instance in the following case with two assemblies:

    ```

         {
           "assemblies": [
             {
               "sites_in_groups": [ [0], [1] ],
               "group_probabilities": [0.2, 0.8]
             },
             {
               "sites_in_groups": [ [2], [3] ],
               "group_probabilities": [0.3, 0.7]
             }
           ]
         }
    ```

    Site 0 is present with a probability of 20 % and site 1 with a probability of 80 %. These two sites are correlated (either site 0 or 1 is present). Similarly, site 2 is present with a probability of 30 % and site 3 with a probability of 70 %.
    These two sites are correlated (either site 2 or 3 is present).
    However, the presence or absence of sites 0 and 1 is not correlated with the presence or absence of sites 2 and 3 (in the specific example, the pair of sites (0, 2) can occur with 0.2*0.3 = 6 % probability; the pair (0, 3) with 0.2*0.7 = 14 % probability; the pair (1, 2) with 0.8*0.3 = 24 % probability; and the pair (1, 3) with 0.8*0.7 = 56 % probability).

**Examples:**

- `{'sites_in_groups': [[0], [1]], 'group_probabilities': [0.3, 0.7]}`
- `{'sites_in_groups': [[1, 2], [3]], 'group_probabilities': [0.3, 0.7]}`

**Formats:** [[JSON](assemblies.json)] [[MD](assemblies.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/assemblies",
    "title": "Assemblies",
    "x-optimade-type": "dictionary",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "assembiles"
    },
    "type": [
        "object",
        "null"
    ],
    "description": "A description of groups of sites that are statistically correlated.\n\n**Requirements/Conventions**:\n\n- The property SHOULD be `null` for entries that have no partial occupancies.\n- If present, the correct flag MUST be set in the list `structure_features` (see property `structure_features`).\n- Client implementations MUST check its presence (as its presence changes the interpretation of the structure).\n- If present, it MUST be a list of dictionaries, each of which represents an assembly and MUST have the following two keys:\n\n  - **sites_in_groups**: Index of the sites (0-based) that belong to each group for each assembly.\n\n    Example: `[[1], [2]]`: two groups, one with the second site, one with the third.\n    Example: `[[1,2], [3]]`: one group with the second and third site, one with the fourth.\n\n  - **group_probabilities**: Statistical probability of each group. It MUST have the same length as `sites_in_groups`.\n    It SHOULD sum to one.\n    See below for examples of how to specify the probability of the occurrence of a vacancy.\n    The possible reasons for the values not to sum to one are the same as already specified above for the `concentration` of each `species`, see property `species`.\n\n- If a site is not present in any group, it means that it is present with 100 % probability (as if no assembly was specified).\n- A site MUST NOT appear in more than one group.\n\n**Explained examples**:\n\n- `{\"sites_in_groups\": [[0], [1]], \"group_probabilities\": [0.3, 0.7]}`: the first site and the second site never occur at the same time in the unit cell.\n  Statistically, 30 % of the times the first site is present, while 70 % of the times the second site is present.\n- `{\"sites_in_groups\": [[1,2], [3]], \"group_probabilities\": [0.3, 0.7]}`: the second and third sites are either present together or not present; they form the first group of atoms for this assembly.\n  The second group is formed by the fourth site.\n  Sites of the first group (the second and the third) are never present at the same time as the fourth site.\n  30 % of times sites 1 and 2 are present (and site 3 is absent); 70 % of times site 3 is present (and sites 1 and 2 are absent).\n\n- **Notes**:\n\n  - Assemblies are essential to represent, for instance, the situation where an atom can statistically occupy two different positions (sites).\n  - By defining groups, it is possible to represent, e.g., the case where a functional molecule (and not just one atom) is either present or absent (or the case where it is present in two conformations).\n  - Considerations on virtual alloys and on vacancies: In the special case of a virtual alloy, these specifications allow two different, equivalent ways of specifying them.\n    For instance, for a site at the origin with 30 % probability of being occupied by Si, 50 % probability of being occupied by Ge, and 20 % of being a vacancy, the following two representations are possible:\n\n    - Using a single species:\n\n      ```\n\n           {\n             \"cartesian_site_positions\": [[0,0,0]],\n             \"species_at_sites\": [\"SiGe-vac\"],\n             \"species\": [\n               {\n                 \"name\": \"SiGe-vac\",\n                 \"chemical_symbols\": [\"Si\", \"Ge\", \"vacancy\"],\n                 \"concentration\": [0.3, 0.5, 0.2]\n               }\n             ]\n             // ...\n           }\n      ```\n\n\n    - Using multiple species and the assemblies:\n\n      ```\n\n           {\n             \"cartesian_site_positions\": [ [0,0,0], [0,0,0], [0,0,0] ],\n             \"species_at_sites\": [\"Si\", \"Ge\", \"vac\"],\n             \"species\": [\n               { \"name\": \"Si\", \"chemical_symbols\": [\"Si\"], \"concentration\": [1.0] },\n               { \"name\": \"Ge\", \"chemical_symbols\": [\"Ge\"], \"concentration\": [1.0] },\n               { \"name\": \"vac\", \"chemical_symbols\": [\"vacancy\"], \"concentration\": [1.0] }\n             ],\n             \"assemblies\": [\n               {\n                 \"sites_in_groups\": [ [0], [1], [2] ],\n                 \"group_probabilities\": [0.3, 0.5, 0.2]\n               }\n             ]\n             // ...\n           }\n      ```\n\n  - It is up to the database provider to decide which representation to use, typically depending on the internal format in which the structure is stored.\n    However, given a structure identified by a unique ID, the API implementation MUST always provide the same representation for it.\n  - The probabilities of occurrence of different assemblies are uncorrelated.\n    So, for instance in the following case with two assemblies:\n\n    ```\n\n         {\n           \"assemblies\": [\n             {\n               \"sites_in_groups\": [ [0], [1] ],\n               \"group_probabilities\": [0.2, 0.8]\n             },\n             {\n               \"sites_in_groups\": [ [2], [3] ],\n               \"group_probabilities\": [0.3, 0.7]\n             }\n           ]\n         }\n    ```\n\n    Site 0 is present with a probability of 20 % and site 1 with a probability of 80 %. These two sites are correlated (either site 0 or 1 is present). Similarly, site 2 is present with a probability of 30 % and site 3 with a probability of 70 %.\n    These two sites are correlated (either site 2 or 3 is present).\n    However, the presence or absence of sites 0 and 1 is not correlated with the presence or absence of sites 2 and 3 (in the specific example, the pair of sites (0, 2) can occur with 0.2*0.3 = 6 % probability; the pair (0, 3) with 0.2*0.7 = 14 % probability; the pair (1, 2) with 0.8*0.3 = 24 % probability; and the pair (1, 3) with 0.8*0.7 = 56 % probability).",
    "examples": [
        {
            "sites_in_groups": [
                [
                    0
                ],
                [
                    1
                ]
            ],
            "group_probabilities": [
                0.3,
                0.7
            ]
        },
        {
            "sites_in_groups": [
                [
                    1,
                    2
                ],
                [
                    3
                ]
            ],
            "group_probabilities": [
                0.3,
                0.7
            ]
        }
    ],
    "x-optimade-unit": "inapplicable",
    "properties": {
        "sites_in_groups": {
            "title": "Sites in groups",
            "x-optimade-type": "list",
            "type": [
                "array"
            ],
            "description": "Index of the sites (0-based) that belong to each group for each assembly.\n\n**Explained examples**:\n\n- `[[1], [2]]`: two groups, one with the second site, one with the third.\n- `[[1,2], [3]]`: one group with the second and third site, one with the fourth.",
            "examples": [
                [
                    [
                        1
                    ],
                    [
                        2
                    ]
                ],
                [
                    [
                        1,
                        2
                    ],
                    [
                        3
                    ]
                ]
            ],
            "x-optimade-unit": "inapplicable",
            "items": {
                "title": "Group of sites",
                "x-optimade-type": "list",
                "type": [
                    "array"
                ],
                "description": "A list of sites that belong to one group in the assembly.",
                "examples": [
                    [
                        1
                    ],
                    [
                        1,
                        2
                    ]
                ],
                "x-optimade-unit": "inapplicable",
                "items": {
                    "title": "A site reference",
                    "x-optimade-type": "integer",
                    "type": [
                        "integer"
                    ],
                    "description": "An integer that refers to a site by index (0-based).",
                    "examples": [
                        2
                    ],
                    "x-optimade-unit": "inapplicable"
                }
            }
        },
        "group_probabilities": {
            "title": "Group probabilities",
            "x-optimade-type": "list",
            "type": [
                "array"
            ],
            "description": "Statistical probability of each group.\n\n**Requirements/Conventions**:\n\n- It MUST have the same length as `sites_in_groups`.\n- It SHOULD sum to one.\n- The possible reasons for the values not to sum to one are the same as specified in the `concentration` field of the `species` property.",
            "examples": [
                [
                    0.3,
                    0.7
                ]
            ],
            "x-optimade-unit": "inapplicable",
            "items": {
                "title": "A concentration",
                "x-optimade-type": "float",
                "type": [
                    "number"
                ],
                "description": "An float that specifies the statistical probability of a group in the description of assemblies.",
                "examples": [
                    0.4
                ],
                "x-optimade-unit": "dimensionless"
            }
        }
    },
    "required": [
        "sites_in_groups",
        "group_probabilities"
    ],
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```