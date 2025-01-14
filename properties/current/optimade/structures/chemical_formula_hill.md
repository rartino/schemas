# Hill chemical formula (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_hill`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_hill)**  
**Definition name:** `chemical_formula_hill`

**Property name:** Hill chemical formula  
**Description:** The chemical formula for a structure in [Hill form](https://dx.doi.org/10.1021/ja02046a005) with element symbols followed by integer chemical proportion numbers. The proportion number MUST be omitted if it is 1.  
**Type:** string  

**Requirements/Conventions**:

- The overall scale factor of the chemical proportions is chosen such that the resulting values are integers that indicate the most chemically relevant unit of which the system is composed.
  For example, if the structure is a repeating unit cell with four hydrogens and four oxygens that represents two hydroperoxide molecules, `chemical_formula_hill` is `"H2O2"` (i.e., not `"HO"`, nor `"H4O4"`).
- If the chemical insight needed to ascribe a Hill formula to the system is not present, the property MUST be handled as unset.
- Element symbols MUST have proper capitalization (e.g., `"Si"`, not `"SI"` for "silicon").
- Elements MUST be placed in [Hill order](https://dx.doi.org/10.1021/ja02046a005>), followed by their integer chemical proportion number.
  Hill order means: if carbon is present, it is placed first, and if also present, hydrogen is placed second.
  After that, all other elements are ordered alphabetically.
  If carbon is not present, all elements are ordered alphabetically.
- If the system has sites with partial occupation and the total occupations of each element do not all sum up to integers, then the Hill formula SHOULD be handled as unset.
- No spaces or separators are allowed.

**Query examples**:

- A filter that matches an exactly given formula is `chemical_formula_hill="H2O2"`.

**Examples:**

- `H2O2`

**Formats:** [[JSON](chemical_formula_hill.json)] [[MD](chemical_formula_hill.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_hill",
    "title": "Hill chemical formula",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "chemical_formula_hill"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "The chemical formula for a structure in [Hill form](https://dx.doi.org/10.1021/ja02046a005) with element symbols followed by integer chemical proportion numbers. The proportion number MUST be omitted if it is 1.\n\n**Requirements/Conventions**:\n\n- The overall scale factor of the chemical proportions is chosen such that the resulting values are integers that indicate the most chemically relevant unit of which the system is composed.\n  For example, if the structure is a repeating unit cell with four hydrogens and four oxygens that represents two hydroperoxide molecules, `chemical_formula_hill` is `\"H2O2\"` (i.e., not `\"HO\"`, nor `\"H4O4\"`).\n- If the chemical insight needed to ascribe a Hill formula to the system is not present, the property MUST be handled as unset.\n- Element symbols MUST have proper capitalization (e.g., `\"Si\"`, not `\"SI\"` for \"silicon\").\n- Elements MUST be placed in [Hill order](https://dx.doi.org/10.1021/ja02046a005>), followed by their integer chemical proportion number.\n  Hill order means: if carbon is present, it is placed first, and if also present, hydrogen is placed second.\n  After that, all other elements are ordered alphabetically.\n  If carbon is not present, all elements are ordered alphabetically.\n- If the system has sites with partial occupation and the total occupations of each element do not all sum up to integers, then the Hill formula SHOULD be handled as unset.\n- No spaces or separators are allowed.\n\n**Query examples**:\n\n- A filter that matches an exactly given formula is `chemical_formula_hill=\"H2O2\"`.",
    "examples": [
        "H2O2"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```