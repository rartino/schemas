# Bohr magneton, \(\mu_B\) (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/codata/1969/electromagnetic/bohrmagneton`](https://schemas.optimade.org/units/v1.2.0/codata/1969/electromagnetic/bohrmagneton)**  
**Definition name:** `bohrmagneton`

**Unit name:** Bohr magneton  
**Latin symbol:** bohrmagneton  
**Display symbol:** \(\mu_B\)  
  
**Description:** A unit expressing the magnetic moment of an electron caused by its orbital or spin angular momentum defined as part of CODATA 1969.

"The magneton moment of the free electron in units of the Bohr magneton \(\mu_B=e\hbar/2m_e\)" [B. N. Taylor, W. H. Parker, and D. N. Langenberg, Rev. Mod. Phys. 41(3), 375-496 (1969)]

**Resources:**

- [Defining paper: B. N. Taylor, W. H. Parker, and D. N. Langenberg, Rev. Mod. Phys. 41(3), 375-496 (1969)](https://doi.org/10.1103/RevModPhys.41.375)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Bohr_magneton)


**Formats:** [[JSON](bohrmagneton.json)] [[MD](bohrmagneton.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/codata/1969/electromagnetic/bohrmagneton",
    "title": "Bohr magneton",
    "symbol": "bohrmagneton",
    "display-symbol": "\\(\\mu_B\\)",
    "description": "A unit expressing the magnetic moment of an electron caused by its orbital or spin angular momentum defined as part of CODATA 1969.\n\n\"The magneton moment of the free electron in units of the Bohr magneton \\(\\mu_B=e\\hbar/2m_e\\)\" [B. N. Taylor, W. H. Parker, and D. N. Langenberg, Rev. Mod. Phys. 41(3), 375-496 (1969)]",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "bohrmagneton"
    },
    "resources": [
        {
            "relation": "Defining paper: B. N. Taylor, W. H. Parker, and D. N. Langenberg, Rev. Mod. Phys. 41(3), 375-496 (1969)",
            "resource-id": "https://doi.org/10.1103/RevModPhys.41.375"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Bohr_magneton"
        }
    ],
    "approximate-relations": [
        {
            "base-units": [
                {
                    "symbol": "bohrmagneton",
                    "id": "https://schema.optimade.org/constants/v1.2.0/codata/2018/electromagnetic/bohrmagneton"
                }
            ],
            "base-units-expression": "bohrmagneton"
        }
    ],
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "bohrmagneton"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```