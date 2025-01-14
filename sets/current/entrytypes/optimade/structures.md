# Structures (entrytype)
This page documents an [OPTIMADE](https://www.optimade.org/) [Entrytype Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/sets/v1.2.0/entrytypes/optimade/structures`](https://schemas.optimade.org/sets/v1.2.0/entrytypes/optimade/structures)**  
**Definition name:** `structures`

**Entrytype name:** Structures  
**Description:** The structures entry type describes a crystal structure via its unit cell  

**Formats:** [[JSON](structures.json)] [[MD](structures.md)]

This entrytype defines the following properties:

* **[ID](../../../../properties/v1.2.0/core/id)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/id`](https://schemas.optimade.org/properties/v1.2.0/core/id)  
  A unique string referencing a specific entry in the database.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST always be included in the response.
    - Taken together, the ID and entry type MUST uniquely identify the entry.
    - Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.
    - IDs MAY change over time.


* **[Type](../../../../properties/v1.2.0/core/type)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/type`](https://schemas.optimade.org/properties/v1.2.0/core/type)  
  The name of the type of an entry.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST always be included in the response.
    - MUST be an existing entry type.
    - The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.


* **[Immutable ID (immutable_id)](../../../../properties/v1.2.0/core/immutable_id)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/immutable_id`](https://schemas.optimade.org/properties/v1.2.0/core/immutable_id)  
  The entry's immutable ID (e.g., a UUID).

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - This is important for databases having preferred IDs that point to "the latest version" of a record, but still offer access to older variants.
    - This ID maps to the version-specific record, in case it changes in the future.


* **[Last modified (last_modified)](../../../../properties/v1.2.0/core/last_modified)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/last_modified`](https://schemas.optimade.org/properties/v1.2.0/core/last_modified)  
  Date and time representing when the entry was last modified.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[Elements](../../../../properties/v1.2.0/optimade/structures/elements)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements)  
  The chemical symbols of the different elements present in the structure.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - The strings are the chemical symbols, i.e., either a single uppercase letter or an uppercase letter followed by a number of lowercase letters.
    - The order MUST be alphabetical.
    - MUST refer to the same elements in the same order, and therefore be of the same length, as `elements_ratios`, if the latter is provided.
    - Note: This property SHOULD NOT contain the string "X" to indicate non-chemical elements or "vacancy" to indicate vacancies (in contrast to the field `chemical_symbols` for the species property).
    
    **Query examples**:
    
    - A filter that matches all records of structures that contain Si, Al **and** O, and possibly other elements: `elements HAS ALL "Si", "Al", "O"`.
    - To match structures with exactly these three elements, use `elements HAS ALL "Si", "Al", "O" AND elements LENGTH 3`.
    - Note: length queries on this property can be equivalently formulated by filtering on the `nelements` property directly.


* **[Number of elements (nelements)](../../../../properties/v1.2.0/optimade/structures/nelements)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nelements`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nelements)  
  Number of different elements in the structure as an integer.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - MUST be equal to the lengths of the list properties elements and elements_ratios, if they are provided.
    
    **Querying**:
    
    - Queries on this property can equivalently be formulated using `elements LENGTH`.
    - A filter that matches structures that have exactly 4 elements: `nelements=4`.
    - A filter that matches structures that have between 2 and 7 elements: `nelements>=2 AND nelements<=7`.


* **[Elements ratios (elements_ratios)](../../../../properties/v1.2.0/optimade/structures/elements_ratios)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements_ratios`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements_ratios)  
  Relative proportions of different elements in the structure.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - Composed by the proportions of elements in the structure as a list of floating point numbers.
    - The sum of the numbers MUST be 1.0 (within floating point accuracy)
    - MUST refer to the same elements in the same order, and therefore be of the same length, as `elements`, if the latter is provided.
    
    **Query examples**:
    
    - Note: Useful filters can be formulated using the set operator syntax for correlated values.
      However, since the values are floating point values, the use of equality comparisons is generally inadvisable.
    - OPTIONAL: a filter that matches structures where approximately 1/3 of the atoms in the structure are the element Al is: `elements:elements_ratios HAS ALL "Al":>0.3333, "Al":<0.3334`.


* **[Descriptive chemical formula (chemical_formula_descriptive)](../../../../properties/v1.2.0/optimade/structures/chemical_formula_descriptive)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_descriptive`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_descriptive)  
  The chemical formula for a structure as a string in a form chosen by the API implementation.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - The chemical formula is given as a string consisting of properly capitalized element symbols followed by integers or decimal numbers, balanced parentheses, square, and curly brackets `(`,\ `)`, `[`,\ `]`, `{`, `}`, commas, the `+`, `-`, `:` and `=` symbols.
      The parentheses are allowed to be followed by a number.
      Spaces are allowed anywhere except within chemical symbols.
      The order of elements and any groupings indicated by parentheses or brackets are chosen freely by the API implementation.
    - The string SHOULD be arithmetically consistent with the element ratios in the `chemical_formula_reduced` property.
    - It is RECOMMENDED, but not mandatory, that symbols, parentheses and brackets, if used, are used with the meanings prescribed by [IUPAC's Nomenclature of Organic Chemistry](https://www.qmul.ac.uk/sbcs/iupac/bibliog/blue.html).
    
    **Query examples**:
    
    - Note: the free-form nature of this property is likely to make queries on it across different databases inconsistent.
    - A filter that matches an exactly given formula: `chemical_formula_descriptive="(H2O)2 Na"`.
    - A filter that does a partial match: `chemical_formula_descriptive CONTAINS "H2O"`.


* **[Reduced chemical formula (chemical_formula_reduced)](../../../../properties/v1.2.0/optimade/structures/chemical_formula_reduced)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_reduced`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_reduced)  
  The reduced chemical formula for a structure as a string with element symbols and integer chemical proportion numbers.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be queryable using the OPTIMADE filter language equality and inequality operators. Other filter language features do not need to be available.
    - **Response:** MAY be included by default in the response.
    - Intricate queries on formula components are suggested to be formulated using set-type filter operators on the multi valued `elements` and `elements_ratios` properties.
    - Element symbols MUST have proper capitalization (e.g., `"Si"`, not `"SI"` for "silicon").
    - Elements MUST be placed in alphabetical order, followed by their integer chemical proportion number.
    - For structures with no partial occupation, the chemical proportion numbers are the smallest integers for which the chemical proportion is exactly correct.
    - For structures with partial occupation, the chemical proportion numbers are integers that within reasonable approximation indicate the correct chemical proportions. The precise details of how to perform the rounding is chosen by the API implementation.
    - No spaces or separators are allowed.
    
    **Query examples**:
    
    - A filter that matches an exactly given formula is `chemical_formula_reduced="H2NaO"`.


* **[Hill chemical formula (chemical_formula_hill)](../../../../properties/v1.2.0/optimade/structures/chemical_formula_hill)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_hill`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_hill)  
  The chemical formula for a structure in [Hill form](https://dx.doi.org/10.1021/ja02046a005) with element symbols followed by integer chemical proportion numbers. The proportion number MUST be omitted if it is 1.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
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


* **[Anonymous chemical formula (chemical_formula_anonymous)](../../../../properties/v1.2.0/optimade/structures/chemical_formula_anonymous)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_anonymous`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_anonymous)  
  The anonymous formula is the chemical_formula_reduced, but where the elements are instead first ordered by their chemical proportion number, and then, in order left to right, replaced by anonymous symbols A, B, C, ..., Z, Aa, Ba, ..., Za, Ab, Bb, ... and so on.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be queryable using the OPTIMADE filter language equality and inequality operators. Other filter language features do not need to be available.
    - **Response:** MAY be included by default in the response.

* **[Dimension types (dimension_types)](../../../../properties/v1.2.0/optimade/structures/dimension_types)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/dimension_types`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/dimension_types)  
  List of three integers describing the periodicity of the boundaries of the unit cell. For each direction indicated by the three lattice_vectors, this list indicates if the direction is periodic (value 1) or non-periodic (value 0). Note: the elements in this list each refer to the direction of the corresponding entry in lattice_vectors and not the Cartesian x, y, z directions.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - MUST be a list of length 3.
    - Each integer element MUST assume only the value 0 or 1.
    
    **Explained examples**:
    
    - A nonperiodic structure, for example, for a single molecule : `[0, 0, 0]`
    - A unit cell that is periodic in the direction of the third lattice vector, for example for a carbon nanotube: `[0, 0, 1]`
    - For a 2D surface/slab, with a unit cell that is periodic in the direction of the first and third lattice vectors: `[1, 0, 1]`
    - For a bulk 3D system with a unit cell that is periodic in all directions: `[1, 1, 1]`


* **[Number of periodic dimensions (nperiodic_dimensions)](../../../../properties/v1.2.0/optimade/structures/nelements)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nelements`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nelements)  
  An integer specifying the number of periodic dimensions in the structure, equivalent to the number of non-zero entries in `dimension_types`.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - The integer value MUST be between 0 and 3 inclusive and MUST be equal to the sum of the items in the dimension_types property.
    
    - This property only reflects the treatment of the lattice vectors provided for the structure, and not any physical interpretation of the dimensionality of its contents.
    
    **Explained examples**
    
    - `2` should be indicated in cases where dimension_types is any of `[1, 1, 0]`, `[1, 0, 1]`, `[0, 1, 1]`.
    
    **Query examples**:
    
    - Match only structures with exactly 3 periodic dimensions: `nperiodic_dimensions=3`
    - Match all structures with 2 or fewer periodic dimensions: `nperiodic_dimensions<=2`


* **[Lattice vectors (lattice_vectors)](../../../../properties/v1.2.0/optimade/structures/lattice_vectors)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/lattice_vectors`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/lattice_vectors)  
  The three lattice vectors in Cartesian coordinates, in ångström (Å).

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
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


* **[Hall space group (space_group_hall)](../../../../properties/v1.2.0/optimade/structures/space_group_hall)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/space_group_hall`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/space_group_hall)  
  A Hall space group symbol representing the symmetry of the structure as defined in Hall, S. R. (1981), Acta Cryst. A37, 517-525 and erratum (1981), A37, 921.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - Each component of the Hall symbol MUST be separated by a single space symbol.
    - If there exists a standard Hall symbol which represents the symmetry it SHOULD be used.
    - MUST be null if n`periodic_dimensions` is not equal to 3.


* **[Space group IT number (space_group_it_number)](../../../../properties/v1.2.0/optimade/structures/space_group_it_number)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/space_group_it_number`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/space_group_it_number)  
  Space group number for the structure assigned by the International Tables for Crystallography Vol. A.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - The integer value MUST be between 1 and 230.
    - MUST be null if `nperiodic_dimensions` is not equal to 3.


* **[Cartesian site positions (cartesian_site_positions)](../../../../properties/v1.2.0/optimade/structures/cartesian_site_positions)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/cartesian_site_positions`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/cartesian_site_positions)  
  Cartesian positions of each site in the structure.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    A site is usually used to describe positions of atoms; what atoms can be encountered at a given site is conveyed by the `species_at_sites` property, and the species themselves are described in the `species` property.
    
    **Requirements/Conventions**:
    
    - It MUST be a list of length equal to the number of sites in the structure, where every element is a list of the three Cartesian coordinates of a site expressed as float values in the unit angstrom (Å).
    - An entry MAY have multiple sites at the same Cartesian position (for a relevant use of this, see e.g., the property `assemblies`).
    
    **Explained examples**:
    
    - `[[0,0,0],[0,0,2]]` indicates a structure with two sites, one sitting at the origin and one along the (positive) *z*-axis, 2 Å away from the origin.


* **[Number of sites (nsites)](../../../../properties/v1.2.0/optimade/structures/nsites)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nsites`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nsites)  
  An integer specifying the length of the `cartesian_site_positions` property.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - MUST be equal to the lengths of the list properties elements and elements_ratios, if they are provided.
    
    **Query examples**:
    
    - Match only structures with exactly 4 sites: `nsites=4`
    - Match structures that have between 2 and 7 sites: `nsites>=2 AND nsites<=7`


* **[Species at sites (species_at_sites)](../../../../properties/v1.2.0/optimade/structures/species_at_sites)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/species_at_sites`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/species_at_sites)  
  Name of the species at each site (where values for sites are specified with the same order of the property `cartesian_site_positions`). The properties of the species are found in the property `species`.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - MUST have length equal to the number of sites in the structure (first dimension of the list property `cartesian_site_positions`).
    - Each species name mentioned in the `species_at_sites` list MUST be described in the list property `species` (i.e. for each value in the `species_at_sites` list there MUST exist exactly one dictionary in the `species` list with the `name` attribute equal to the corresponding `species_at_sites` value).
    - Each site MUST be associated only to a single species.
      **Note**: However, species can represent mixtures of atoms, and multiple species MAY be defined for the same chemical element.
      This latter case is useful when different atoms of the same type need to be grouped or distinguished, for instance in simulation codes to assign different initial spin states.
    
    **Explained examples**:
    
    - `["Ti","O2"]` indicates that the first site is hosting a species labeled `"Ti"` and the second a species labeled `"O2"`
    - `["Ac", "Ac", "Ag", "Ir"]` indicates that the first two sites contain the `"Ac"` species, while the third and fourth sites contain the `"Ag"` and `"Ir"` species, respectively.


* **[Species](../../../../properties/v1.2.0/optimade/structures/species)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/species`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/species)  
  A list describing the species of the sites of this structure. Species can represent pure chemical elements, virtual-crystal atoms representing a statistical occupation of a given site by multiple chemical elements, and/or a location to which there are attached atoms, i.e., atoms whose precise location are unknown beyond that they are attached to that position (frequently used to indicate hydrogen atoms attached to another element, e.g., a carbon with three attached hydrogens might represent a methyl group, -CH3).

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - Each list member MUST be a dictionary with the following keys:
    
      - **name**: REQUIRED; gives the name of the species; the **name** value MUST be unique in the `species` list;
    
      - **chemical\_symbols**: REQUIRED; MUST be a list of strings of all chemical elements composing this species. Each item of the list MUST be one of the following:
    
        - a valid chemical-element symbol, or
        - the special value `"X"` to represent a non-chemical element, or
        - the special value `"vacancy"` to represent that this site has a non-zero probability of having a vacancy (the respective probability is indicated in the `concentration` list, see below).
    
        If any one entry in the `species` list has a `chemical_symbols` list that is longer than 1 element, the correct flag MUST be set in the list `structure_features` (see property `structure_features`).
    
      - **concentration**: REQUIRED; MUST be a list of floats, with same length as `chemical_symbols`. The numbers represent the relative concentration of the corresponding chemical symbol in this species.
        The numbers SHOULD sum to one. Cases in which the numbers do not sum to one typically fall only in the following two categories:
    
        - Numerical errors when representing float numbers in fixed precision, e.g. for two chemical symbols with concentrations `1/3` and `2/3`, the concentration might look something like `[0.33333333333, 0.66666666666]`. If the client is aware that the sum is not one because of numerical precision, it can renormalize the values so that the sum is exactly one.
        - Experimental errors in the data present in the database. In this case, it is the responsibility of the client to decide how to process the data.
    
        Note that concentrations are uncorrelated between different sites (even of the same species).
    
      - **attached**: OPTIONAL; if provided MUST be a list of length 1 or more of strings of chemical symbols for the elements attached to this site, or "X" for a non-chemical element.
      - **nattached**: OPTIONAL; if provided MUST be a list of length 1 or more of integers indicating the number of attached atoms of the kind specified in the value of the `attached` key.
    
        The implementation MUST include either both or none of the `attached` and `nattached` keys, and if they are provided, they MUST be of the same length.
        Furthermore, if they are provided, the `structure_features` property MUST include the string `site_attachments`.
    
      - **mass**: OPTIONAL. If present MUST be a list of floats, with the same length as `chemical_symbols`, providing element masses expressed in a.m.u.
        Elements denoting vacancies MUST have masses equal to 0.
      - **original\_name**: OPTIONAL. Can be any valid Unicode string, and SHOULD contain (if specified) the name of the species that is used internally in the source database.
    
            **Note**: With regard to "source database", we refer to the immediate source being queried via the OPTIMADE API implementation.
            The main use of this field is for source databases that use species names, containing characters that are not allowed (see description of the list property `species_at_sites`).
    
    - For systems that have only species formed by a single chemical symbol, and that have at most one species per chemical symbol, SHOULD use the chemical symbol as species name (e.g., `"Ti"` for titanium, `"O"` for oxygen, etc.)
      However, note that this is OPTIONAL, and client implementations MUST NOT assume that the key corresponds to a chemical symbol, nor assume that if the species name is a valid chemical symbol, that it represents a species with that chemical symbol.
      This means that a species `{"name": "C", "chemical_symbols": ["Ti"], "concentration": [1.0]}` is valid and represents a titanium species (and *not* a carbon species).
    - It is NOT RECOMMENDED that a structure includes species that do not have at least one corresponding site.
    
    **Explained examples**:
    
    - `[ {"name": "Ti", "chemical_symbols": ["Ti"], "concentration": [1.0]} ]`: any site with this species is occupied by a Ti atom.
    - `[ {"name": "Ti", "chemical_symbols": ["Ti", "vacancy"], "concentration": [0.9, 0.1]} ]`: any site with this species is occupied by a Ti atom with 90 % probability, and has a vacancy with 10 % probability.
    - `[ {"name": "BaCa", "chemical_symbols": ["vacancy", "Ba", "Ca"], "concentration": [0.05, 0.45, 0.5], "mass": [0.0, 137.327, 40.078]} ]`: any site with this species is occupied by a Ba atom with 45 % probability, a Ca atom with 50 % probability, and by a vacancy with 5 % probability.
    - `[ {"name": "C12", "chemical_symbols": ["C"], "concentration": [1.0], "mass": [12.0]} ]`: any site with this species is occupied by a carbon isotope with mass 12.
    - `[ {"name": "C13", "chemical_symbols": ["C"], "concentration": [1.0], "mass": [13.0]} ]`: any site with this species is occupied by a carbon isotope with mass 13.
    - `[ {"name": "CH3", "chemical_symbols": ["C"], "concentration": [1.0], "attached": ["H"], "nattached": [3]} ]`: any site with this species is occupied by a methyl group, -CH3, which is represented without specifying precise positions of the hydrogen atoms.


* **[Assemblies](../../../../properties/v1.2.0/optimade/structures/assemblies)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structures/assemblies`](https://schemas.optimade.org/properties/v1.2.0/optimade/structures/assemblies)  
  A description of groups of sites that are statistically correlated.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
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


* **[Structure features (structure_features)](../../../../properties/v1.2.0/optimade/structure/structure_features)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/structure/structure_features`](https://schemas.optimade.org/properties/v1.2.0/optimade/structure/structure_features)  
  A list of strings that flag which special features are used by the structure.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - MUST be an empty list if no special features are used.
    - MUST be sorted alphabetically.
    - If a special feature listed below is used, the list MUST contain the corresponding string.
    - If a special feature listed below is not used, the list MUST NOT contain the corresponding string.
    - **List of strings used to indicate special structure features:**
      - `disorder`: this flag MUST be present if any one entry in the species list has a `chemical_symbols` list that is longer than 1 element.
      - `implicit_atoms`: this flag MUST be present if the structure contains atoms that are not assigned to sites via the property `species_at_sites` (e.g., because their positions are unknown). When this flag is present, the properties related to the chemical formula will likely not match the type and count of atoms represented by the `species_at_sites`, `species`, and `assemblies` properties.
      - `site_attachments`: this flag MUST be present if any one entry in the species list includes `attached` and `nattached`.
      - `assemblies`: this flag MUST be present if the property assemblies is present.
    
      **Explained examples**:
      - A structure having implicit atoms and using assemblies: `["assemblies", "implicit_atoms"]`



**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/sets/v1.2.0/entrytypes/optimade/structures",
    "title": "Structures",
    "description": "The structures entry type describes a crystal structure via its unit cell",
    "x-optimade-definition": {
        "kind": "entrytype",
        "format": "1.2",
        "version": "1.2.0",
        "name": "structures"
    },
    "type": "object",
    "properties": {
        "id": {
            "x-optimade-requirements": {
                "support": "must",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "always"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/id",
            "title": "ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "id"
            },
            "type": [
                "string"
            ],
            "description": "A unique string referencing a specific entry in the database.\n\n**Requirements/Conventions:**\n\n- Taken together, the ID and entry type MUST uniquely identify the entry.\n- Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.\n- IDs MAY change over time.",
            "examples": [
                "db/1234567",
                "cod/2000000",
                "cod/2000000@1234567",
                "nomad/L1234567890",
                "42"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "type": {
            "x-optimade-requirements": {
                "support": "must",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "always"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/type",
            "title": "Type",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "type"
            },
            "type": [
                "string"
            ],
            "description": "The name of the type of an entry.\n\n**Requirements/Conventions:**\n\n- MUST be an existing entry type.\n- The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.",
            "examples": [
                "structures"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "immutable_id": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/immutable_id",
            "title": "Immutable ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "immutable_id"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "The entry's immutable ID (e.g., a UUID).\n\n**Requirements/Conventions:**\n\n- This is important for databases having preferred IDs that point to \"the latest version\" of a record, but still offer access to older variants.\n- This ID maps to the version-specific record, in case it changes in the future.",
            "examples": [
                "8bd3e750-b477-41a0-9b11-3a799f21b44f",
                "fjeiwoj,54;@=%<>#32"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "last_modified": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/last_modified",
            "title": "Last modified",
            "x-optimade-type": "timestamp",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "last_modified"
            },
            "type": [
                "string",
                "null"
            ],
            "format": "date-time",
            "description": "Date and time representing when the entry was last modified.",
            "examples": [
                "2007-04-05T14:30:20Z"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "elements": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
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
            }
        },
        "nelements": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nelements",
            "title": "Number of elements",
            "x-optimade-type": "integer",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "nelements"
            },
            "type": [
                "integer",
                "null"
            ],
            "description": "Number of different elements in the structure as an integer.\n\n**Requirements/Conventions**:\n\n- MUST be equal to the lengths of the list properties elements and elements_ratios, if they are provided.\n\n**Querying**:\n\n- Queries on this property can equivalently be formulated using `elements LENGTH`.\n- A filter that matches structures that have exactly 4 elements: `nelements=4`.\n- A filter that matches structures that have between 2 and 7 elements: `nelements>=2 AND nelements<=7`.",
            "examples": [
                3
            ],
            "x-optimade-unit": "dimensionless"
        },
        "elements_ratios": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/elements_ratios",
            "title": "Elements ratios",
            "x-optimade-type": "list",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "element_ratios"
            },
            "type": [
                "array",
                "null"
            ],
            "description": "Relative proportions of different elements in the structure.\n\n**Requirements/Conventions**:\n\n- Composed by the proportions of elements in the structure as a list of floating point numbers.\n- The sum of the numbers MUST be 1.0 (within floating point accuracy)\n- MUST refer to the same elements in the same order, and therefore be of the same length, as `elements`, if the latter is provided.\n\n**Query examples**:\n\n- Note: Useful filters can be formulated using the set operator syntax for correlated values.\n  However, since the values are floating point values, the use of equality comparisons is generally inadvisable.\n- OPTIONAL: a filter that matches structures where approximately 1/3 of the atoms in the structure are the element Al is: `elements:elements_ratios HAS ALL \"Al\":>0.3333, \"Al\":<0.3334`.",
            "examples": [
                [
                    1.0
                ],
                [
                    0.3333333333333333,
                    0.2222222222222222,
                    0.4444444444444444
                ]
            ],
            "x-optimade-unit": "inapplicable",
            "items": {
                "x-optimade-type": "float",
                "type": [
                    "number"
                ],
                "x-optimade-unit": "dimensionless",
                "minimum": 0.0,
                "maximum": 1.0
            }
        },
        "chemical_formula_descriptive": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_descriptive",
            "title": "Descriptive chemical formula",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "chemical_formula_descriptive"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "The chemical formula for a structure as a string in a form chosen by the API implementation.\n\n**Requirements/Conventions**:\n\n- The chemical formula is given as a string consisting of properly capitalized element symbols followed by integers or decimal numbers, balanced parentheses, square, and curly brackets `(`,\\ `)`, `[`,\\ `]`, `{`, `}`, commas, the `+`, `-`, `:` and `=` symbols.\n  The parentheses are allowed to be followed by a number.\n  Spaces are allowed anywhere except within chemical symbols.\n  The order of elements and any groupings indicated by parentheses or brackets are chosen freely by the API implementation.\n- The string SHOULD be arithmetically consistent with the element ratios in the `chemical_formula_reduced` property.\n- It is RECOMMENDED, but not mandatory, that symbols, parentheses and brackets, if used, are used with the meanings prescribed by [IUPAC's Nomenclature of Organic Chemistry](https://www.qmul.ac.uk/sbcs/iupac/bibliog/blue.html).\n\n**Query examples**:\n\n- Note: the free-form nature of this property is likely to make queries on it across different databases inconsistent.\n- A filter that matches an exactly given formula: `chemical_formula_descriptive=\"(H2O)2 Na\"`.\n- A filter that does a partial match: `chemical_formula_descriptive CONTAINS \"H2O\"`.",
            "examples": [
                "(H2O)2 Na",
                "NaCl",
                "CaCO3",
                "CCaO3",
                "(CH3)3N+ - [CH2]2-OH = Me3N+ - CH2 - CH2OH"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "chemical_formula_reduced": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "equality only",
                "response-level": "may",
                "$comment": "If the database store chemical formulas on another format, it may not be possible to search efficiently for anything except equality."
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_reduced",
            "title": "Reduced chemical formula",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "chemical_formula_reduced"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "The reduced chemical formula for a structure as a string with element symbols and integer chemical proportion numbers.\n\n**Requirements/Conventions**:\n\n- Intricate queries on formula components are suggested to be formulated using set-type filter operators on the multi valued `elements` and `elements_ratios` properties.\n- Element symbols MUST have proper capitalization (e.g., `\"Si\"`, not `\"SI\"` for \"silicon\").\n- Elements MUST be placed in alphabetical order, followed by their integer chemical proportion number.\n- For structures with no partial occupation, the chemical proportion numbers are the smallest integers for which the chemical proportion is exactly correct.\n- For structures with partial occupation, the chemical proportion numbers are integers that within reasonable approximation indicate the correct chemical proportions. The precise details of how to perform the rounding is chosen by the API implementation.\n- No spaces or separators are allowed.\n\n**Query examples**:\n\n- A filter that matches an exactly given formula is `chemical_formula_reduced=\"H2NaO\"`.",
            "examples": [
                "H2NaO",
                "ClNa",
                "CCaO3"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "chemical_formula_hill": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
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
            "x-optimade-unit": "inapplicable"
        },
        "chemical_formula_anonymous": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "equality only",
                "response-level": "may",
                "$comment": "If the database store chemical formulas on another format, it may not be possible to search efficiently for anything except equality."
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/chemical_formula_anonymous",
            "title": "Anonymous chemical formula",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "chemical_formula_anonymous"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "The anonymous formula is the chemical_formula_reduced, but where the elements are instead first ordered by their chemical proportion number, and then, in order left to right, replaced by anonymous symbols A, B, C, ..., Z, Aa, Ba, ..., Za, Ab, Bb, ... and so on.",
            "examples": [
                "A2B",
                "A42B42C16D12E10F9G5"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "dimension_types": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
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
            }
        },
        "nperiodic_dimensions": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "all mandatory"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nelements",
            "title": "Number of periodic dimensions",
            "x-optimade-type": "integer",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "nelements"
            },
            "type": [
                "integer",
                "null"
            ],
            "description": "An integer specifying the number of periodic dimensions in the structure, equivalent to the number of non-zero entries in `dimension_types`.\n\n**Requirements/Conventions**:\n\n- The integer value MUST be between 0 and 3 inclusive and MUST be equal to the sum of the items in the dimension_types property.\n\n- This property only reflects the treatment of the lattice vectors provided for the structure, and not any physical interpretation of the dimensionality of its contents.\n\n**Explained examples**\n\n- `2` should be indicated in cases where dimension_types is any of `[1, 1, 0]`, `[1, 0, 1]`, `[0, 1, 1]`.\n\n**Query examples**:\n\n- Match only structures with exactly 3 periodic dimensions: `nperiodic_dimensions=3`\n- Match all structures with 2 or fewer periodic dimensions: `nperiodic_dimensions<=2`",
            "examples": [
                2
            ],
            "x-optimade-unit": "dimensionless"
        },
        "lattice_vectors": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
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
            }
        },
        "space_group_hall": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/space_group_hall",
            "title": "Hall space group",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "space_group_hall"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "A Hall space group symbol representing the symmetry of the structure as defined in Hall, S. R. (1981), Acta Cryst. A37, 517-525 and erratum (1981), A37, 921.\n\n**Requirements/Conventions**:\n\n- Each component of the Hall symbol MUST be separated by a single space symbol.\n- If there exists a standard Hall symbol which represents the symmetry it SHOULD be used.\n- MUST be null if n`periodic_dimensions` is not equal to 3.",
            "examples": [
                "P 2c -2ac",
                "-I 4db 2ab 3"
            ],
            "x-optimade-unit": "unapplicable"
        },
        "space_group_it_number": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/space_group_it_number",
            "title": "Space group IT number",
            "x-optimade-type": "integer",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "space_group_it_number"
            },
            "type": [
                "integer",
                "null"
            ],
            "description": "Space group number for the structure assigned by the International Tables for Crystallography Vol. A.\n\n**Requirements/Conventions**:\n\n- The integer value MUST be between 1 and 230.\n- MUST be null if `nperiodic_dimensions` is not equal to 3.",
            "examples": [
                42
            ],
            "x-optimade-unit": "unapplicable"
        },
        "cartesian_site_positions": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/cartesian_site_positions",
            "title": "Cartesian site positions",
            "x-optimade-type": "list",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "cartesian_site_positions"
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
            "description": "Cartesian positions of each site in the structure.\n\nA site is usually used to describe positions of atoms; what atoms can be encountered at a given site is conveyed by the `species_at_sites` property, and the species themselves are described in the `species` property.\n\n**Requirements/Conventions**:\n\n- It MUST be a list of length equal to the number of sites in the structure, where every element is a list of the three Cartesian coordinates of a site expressed as float values in the unit angstrom (\u00c5).\n- An entry MAY have multiple sites at the same Cartesian position (for a relevant use of this, see e.g., the property `assemblies`).\n\n**Explained examples**:\n\n- `[[0,0,0],[0,0,2]]` indicates a structure with two sites, one sitting at the origin and one along the (positive) *z*-axis, 2 \u00c5 away from the origin.",
            "examples": [
                [
                    [
                        0,
                        0,
                        0
                    ],
                    [
                        0,
                        0,
                        2
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
            }
        },
        "nsites": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "all mandatory"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/nsites",
            "title": "Number of sites",
            "x-optimade-type": "integer",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "nsites"
            },
            "type": [
                "integer",
                "null"
            ],
            "description": "An integer specifying the length of the `cartesian_site_positions` property.\n\n**Requirements/Conventions**:\n\n- MUST be equal to the lengths of the list properties elements and elements_ratios, if they are provided.\n\n**Query examples**:\n\n- Match only structures with exactly 4 sites: `nsites=4`\n- Match structures that have between 2 and 7 sites: `nsites>=2 AND nsites<=7`",
            "examples": [
                42
            ],
            "x-optimade-unit": "dimensionless"
        },
        "species_at_sites": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/species_at_sites",
            "title": "Species at sites",
            "x-optimade-type": "list",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "species_at_sites"
            },
            "type": [
                "array",
                "null"
            ],
            "description": "Name of the species at each site (where values for sites are specified with the same order of the property `cartesian_site_positions`). The properties of the species are found in the property `species`.\n\n**Requirements/Conventions**:\n\n- MUST have length equal to the number of sites in the structure (first dimension of the list property `cartesian_site_positions`).\n- Each species name mentioned in the `species_at_sites` list MUST be described in the list property `species` (i.e. for each value in the `species_at_sites` list there MUST exist exactly one dictionary in the `species` list with the `name` attribute equal to the corresponding `species_at_sites` value).\n- Each site MUST be associated only to a single species.\n  **Note**: However, species can represent mixtures of atoms, and multiple species MAY be defined for the same chemical element.\n  This latter case is useful when different atoms of the same type need to be grouped or distinguished, for instance in simulation codes to assign different initial spin states.\n\n**Explained examples**:\n\n- `[\"Ti\",\"O2\"]` indicates that the first site is hosting a species labeled `\"Ti\"` and the second a species labeled `\"O2\"`\n- `[\"Ac\", \"Ac\", \"Ag\", \"Ir\"]` indicates that the first two sites contain the `\"Ac\"` species, while the third and fourth sites contain the `\"Ag\"` and `\"Ir\"` species, respectively.",
            "examples": [
                [
                    "Ti",
                    "O2"
                ],
                [
                    "Ac",
                    "Ac",
                    "Ag",
                    "Ir"
                ]
            ],
            "x-optimade-unit": "inapplicable",
            "items": {
                "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/common/species_name",
                "title": "Name of the species",
                "x-optimade-type": "string",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "1.2.0",
                    "format": "1.2",
                    "name": "species_name"
                },
                "type": [
                    "string"
                ],
                "description": "The name of the species.",
                "examples": [
                    "Na",
                    "Si[32982]",
                    "quop"
                ],
                "x-optimade-unit": "inapplicable"
            }
        },
        "species": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structures/species",
            "title": "Species",
            "x-optimade-type": "list",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "species"
            },
            "x-optimade-unit-definitions": [
                {
                    "$id": "https://schemas.optimade.org/units/v1.2.0/si/general/atomicmassunit",
                    "title": "atomic mass unit",
                    "symbol": "u",
                    "display-symbol": "u",
                    "alternate-symbols": [
                        "dalton",
                        "Da"
                    ],
                    "description": "A unit of mass representing 1/12 of the mass of a free carbon 12 atom (i.e., a typical value of the mass of a nucleon in an atom) using the current, or one of the historical, definitions given in the editions of The International System of Units (SI).\n\nThe International System of Units (SI), 1st ed. (1970) defines the atomic mass unit in the section \"Units used with the International System\" (known as \"Non-SI units accepted for use with the SI units\" in later editions).\nThe unit is defined in a footnote as: \"The atomic mass unit (unified) is equal to 1/12 of the mass of an atom of the nuclide \u00b9\u00b2C; 1 u = 1.66053 x 10\u207b\u00b2\u2077 kg approximately.\"\n\nThe definition is retained in The International System of Units up to the 7th edition (1998), where the conditions are slightly clarified and dalton (Da) is introduced as an alternative name: \"The unified atomic mass unit is equal to 1/12 of the mass of an unbound atom of the nuclide \u00b9\u00b2C, at rest, and in its ground state. In the field of biochemistry, the unified atomic mass unit is also called the dalton, symbol Da.\"\nIn the 8th ed. (2006) the definition is slightly adjusted, replacing \"unbound\" with \"free\": \"The dalton (Da) and the unified atomic mass unit (u) are alternative names (and symbols) for the same unit, equal to 1/12 times the mass of a free carbon 12 atom, at rest and in its ground state.\"\n\nAll editions of The International System of Units note approximate relationships to the kilogram.\nThe 9th ed. states \"1 Da = 1.660 539 066 60(50)\u00d710\u207b\u00b2\u2077 kg\", where the 2018 CODATA value has been used and the 2019 SI kilogram is referenced (https://schemas.optimade.org/units/v1.2.0/si/2019/base/kilogram).\n\nIn the 2019 redefinition of the SI units, the atomic mass unit is the only unit listed as accepted for use with SI that has an experimental relationship to the base SI units.\n\nThis is a generalized definition taken to reference the current, or one of the historical, SI unit definitions.\nThis definition is intended for situations when it is not possible to be more precise, e.g., in contexts where data have been collected that uses different historical SI definitions.",
                    "compatibility": [
                        "https://schemas.optimade.org/units/v1.2.0/si/1970/accepted/atomicmassunit",
                        "https://schemas.optimade.org/units/v1.2.0/si/1998/accepted/dalton",
                        "https://schemas.optimade.org/units/v1.2.0/si/general/dalton"
                    ],
                    "standard": {
                        "name": "gnu units",
                        "version": "3.15",
                        "symbol": "atomicmassunit"
                    },
                    "resources": [
                        {
                            "relation": "Definition in the International System of Units (SI), 9th Edition",
                            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
                        },
                        {
                            "relation": "Wikipedia article describing the unit",
                            "resource-id": "https://en.wikipedia.org/wiki/Dalton_(unit)"
                        },
                        {
                            "relation": "CODATA unified atomic mass unit fundamental physical constant: source for relationship to kg",
                            "resource-id": "https://physics.nist.gov/cgi-bin/cuu/Value?ukg"
                        }
                    ],
                    "approximate-relations": [
                        {
                            "base-units": [
                                {
                                    "symbol": "kg",
                                    "id": "https://schema.optimade.org/units/v1.2.0/si/general/kilogram"
                                }
                            ],
                            "base-units-expression": "kg",
                            "scale": {
                                "value": 1.6605390666e-27,
                                "standard_uncertainty": 5e-37,
                                "relative_standard_uncertainty": 3e-10
                            }
                        }
                    ],
                    "x-optimade-definition": {
                        "kind": "unit",
                        "format": "1.2",
                        "version": "1.2.0",
                        "name": "atomicmassunit"
                    }
                }
            ],
            "type": [
                "array",
                "null"
            ],
            "description": "A list describing the species of the sites of this structure. Species can represent pure chemical elements, virtual-crystal atoms representing a statistical occupation of a given site by multiple chemical elements, and/or a location to which there are attached atoms, i.e., atoms whose precise location are unknown beyond that they are attached to that position (frequently used to indicate hydrogen atoms attached to another element, e.g., a carbon with three attached hydrogens might represent a methyl group, -CH3).\n\n**Requirements/Conventions**:\n\n- Each list member MUST be a dictionary with the following keys:\n\n  - **name**: REQUIRED; gives the name of the species; the **name** value MUST be unique in the `species` list;\n\n  - **chemical\\_symbols**: REQUIRED; MUST be a list of strings of all chemical elements composing this species. Each item of the list MUST be one of the following:\n\n    - a valid chemical-element symbol, or\n    - the special value `\"X\"` to represent a non-chemical element, or\n    - the special value `\"vacancy\"` to represent that this site has a non-zero probability of having a vacancy (the respective probability is indicated in the `concentration` list, see below).\n\n    If any one entry in the `species` list has a `chemical_symbols` list that is longer than 1 element, the correct flag MUST be set in the list `structure_features` (see property `structure_features`).\n\n  - **concentration**: REQUIRED; MUST be a list of floats, with same length as `chemical_symbols`. The numbers represent the relative concentration of the corresponding chemical symbol in this species.\n    The numbers SHOULD sum to one. Cases in which the numbers do not sum to one typically fall only in the following two categories:\n\n    - Numerical errors when representing float numbers in fixed precision, e.g. for two chemical symbols with concentrations `1/3` and `2/3`, the concentration might look something like `[0.33333333333, 0.66666666666]`. If the client is aware that the sum is not one because of numerical precision, it can renormalize the values so that the sum is exactly one.\n    - Experimental errors in the data present in the database. In this case, it is the responsibility of the client to decide how to process the data.\n\n    Note that concentrations are uncorrelated between different sites (even of the same species).\n\n  - **attached**: OPTIONAL; if provided MUST be a list of length 1 or more of strings of chemical symbols for the elements attached to this site, or \"X\" for a non-chemical element.\n  - **nattached**: OPTIONAL; if provided MUST be a list of length 1 or more of integers indicating the number of attached atoms of the kind specified in the value of the `attached` key.\n\n    The implementation MUST include either both or none of the `attached` and `nattached` keys, and if they are provided, they MUST be of the same length.\n    Furthermore, if they are provided, the `structure_features` property MUST include the string `site_attachments`.\n\n  - **mass**: OPTIONAL. If present MUST be a list of floats, with the same length as `chemical_symbols`, providing element masses expressed in a.m.u.\n    Elements denoting vacancies MUST have masses equal to 0.\n  - **original\\_name**: OPTIONAL. Can be any valid Unicode string, and SHOULD contain (if specified) the name of the species that is used internally in the source database.\n\n        **Note**: With regard to \"source database\", we refer to the immediate source being queried via the OPTIMADE API implementation.\n        The main use of this field is for source databases that use species names, containing characters that are not allowed (see description of the list property `species_at_sites`).\n\n- For systems that have only species formed by a single chemical symbol, and that have at most one species per chemical symbol, SHOULD use the chemical symbol as species name (e.g., `\"Ti\"` for titanium, `\"O\"` for oxygen, etc.)\n  However, note that this is OPTIONAL, and client implementations MUST NOT assume that the key corresponds to a chemical symbol, nor assume that if the species name is a valid chemical symbol, that it represents a species with that chemical symbol.\n  This means that a species `{\"name\": \"C\", \"chemical_symbols\": [\"Ti\"], \"concentration\": [1.0]}` is valid and represents a titanium species (and *not* a carbon species).\n- It is NOT RECOMMENDED that a structure includes species that do not have at least one corresponding site.\n\n**Explained examples**:\n\n- `[ {\"name\": \"Ti\", \"chemical_symbols\": [\"Ti\"], \"concentration\": [1.0]} ]`: any site with this species is occupied by a Ti atom.\n- `[ {\"name\": \"Ti\", \"chemical_symbols\": [\"Ti\", \"vacancy\"], \"concentration\": [0.9, 0.1]} ]`: any site with this species is occupied by a Ti atom with 90 % probability, and has a vacancy with 10 % probability.\n- `[ {\"name\": \"BaCa\", \"chemical_symbols\": [\"vacancy\", \"Ba\", \"Ca\"], \"concentration\": [0.05, 0.45, 0.5], \"mass\": [0.0, 137.327, 40.078]} ]`: any site with this species is occupied by a Ba atom with 45 % probability, a Ca atom with 50 % probability, and by a vacancy with 5 % probability.\n- `[ {\"name\": \"C12\", \"chemical_symbols\": [\"C\"], \"concentration\": [1.0], \"mass\": [12.0]} ]`: any site with this species is occupied by a carbon isotope with mass 12.\n- `[ {\"name\": \"C13\", \"chemical_symbols\": [\"C\"], \"concentration\": [1.0], \"mass\": [13.0]} ]`: any site with this species is occupied by a carbon isotope with mass 13.\n- `[ {\"name\": \"CH3\", \"chemical_symbols\": [\"C\"], \"concentration\": [1.0], \"attached\": [\"H\"], \"nattached\": [3]} ]`: any site with this species is occupied by a methyl group, -CH3, which is represented without specifying precise positions of the hydrogen atoms.",
            "examples": [
                [
                    {
                        "name": "Ti",
                        "chemical_symbols": [
                            "Ti"
                        ],
                        "concentration": [
                            1.0
                        ]
                    }
                ],
                [
                    {
                        "name": "Ti",
                        "chemical_symbols": [
                            "Ti",
                            "vacancy"
                        ],
                        "concentration": [
                            0.9,
                            0.1
                        ]
                    }
                ],
                [
                    {
                        "name": "BaCa",
                        "chemical_symbols": [
                            "vacancy",
                            "Ba",
                            "Ca"
                        ],
                        "concentration": [
                            0.05,
                            0.45,
                            0.5
                        ],
                        "mass": [
                            0.0,
                            137.327,
                            40.078
                        ]
                    }
                ],
                [
                    {
                        "name": "C12",
                        "chemical_symbols": [
                            "C"
                        ],
                        "concentration": [
                            1.0
                        ],
                        "mass": [
                            12.0
                        ]
                    }
                ],
                [
                    {
                        "name": "C13",
                        "chemical_symbols": [
                            "C"
                        ],
                        "concentration": [
                            1.0
                        ],
                        "mass": [
                            13.0
                        ]
                    }
                ],
                [
                    {
                        "name": "CH3",
                        "chemical_symbols": [
                            "C"
                        ],
                        "concentration": [
                            1.0
                        ],
                        "attached": [
                            "H"
                        ],
                        "nattached": [
                            3
                        ]
                    }
                ]
            ],
            "x-optimade-unit": "inapplicable",
            "items": {
                "title": "Species declaration",
                "x-optimade-type": "dictionary",
                "description": "A declaration of a species of the sites of this structure. Species can represent pure chemical elements, virtual-crystal atoms representing a statistical occupation of a given site by multiple chemical elements, and/or a location to which there are attached atoms, i.e., atoms whose precise location are unknown beyond that they are attached to that position (frequently used to indicate hydrogen atoms attached to another element, e.g., a carbon with three attached hydrogens might represent a methyl group, -CH3).",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "object"
                ],
                "properties": {
                    "name": {
                        "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/common/species_name",
                        "title": "Name of the species",
                        "x-optimade-type": "string",
                        "x-optimade-definition": {
                            "kind": "property",
                            "version": "1.2.0",
                            "format": "1.2",
                            "name": "species_name"
                        },
                        "type": [
                            "string"
                        ],
                        "description": "The name of the species.",
                        "examples": [
                            "Na",
                            "Si[32982]",
                            "quop"
                        ],
                        "x-optimade-unit": "inapplicable"
                    },
                    "chemical_symbols": {
                        "title": "Chemical symbols",
                        "x-optimade-type": "list",
                        "type": [
                            "array"
                        ],
                        "description": "The chemical symbols for the elements composing this species.\n\n**Requirements/Conventions**:\n\n- MUST be a list of strings of all chemical elements composing this species.\n  Each item of the list MUST be one of the following:\n\n  - a valid chemical-element symbol, or\n  - the special value `\"X\"` to represent a non-chemical element, or\n  - the special value `\"vacancy\"` to represent that this site has a non-zero probability of having a vacancy (the respective probability is indicated in the `concentration` list, see below).\n\nIf any one entry in the `species` list has a `chemical_symbols` list that is longer than 1 element, the correct flag MUST be set in the list `structure_features` (see property `structure_features`).",
                        "examples": [
                            [
                                "Na",
                                "Cl"
                            ],
                            [
                                "Si",
                                "Mn",
                                "X",
                                "vacancy"
                            ]
                        ],
                        "x-optimade-unit": "inapplicable",
                        "items": {
                            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/common/chemical_symbol_or_vacancy",
                            "title": "Chemical symbol or vacancy",
                            "x-optimade-type": "string",
                            "x-optimade-definition": {
                                "kind": "property",
                                "version": "1.2.0",
                                "format": "1.2",
                                "name": "chemical_symbol_or_vacancy"
                            },
                            "description": "A chemical symbol refering to an element, a non-chemical element, or a vacancy.\n\n**Requirements/Conventions:**\n\n- Must be one of the following:\n\n  - a valid chemical-element symbol, or\n  - the special value `\"X\"` to represent a non-chemical element, or\n  - the special value `\"vacancy\"` to represent that this site has a non-zero probability of having a vacancy (the respective probability is indicated in the `concentration` list, see below).",
                            "x-optimade-unit": "inapplicable",
                            "examples": [
                                "He",
                                "X",
                                "vacancy"
                            ],
                            "type": [
                                "string"
                            ],
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
                        }
                    },
                    "concentration": {
                        "title": "Concentration",
                        "x-optimade-type": "list",
                        "type": [
                            "array"
                        ],
                        "description": "A list of the relative concentrations of the elements composing this species.\n\n**Requirements/Conventions**:\n\n- MUST be a list of floats, with same length as `chemical_symbols`. The numbers represent the relative concentration of the corresponding chemical symbol in this species.\n- The numbers SHOULD sum to one. Cases in which the numbers do not sum to one typically fall only in the following two categories:\n\n  - Numerical errors when representing float numbers in fixed precision, e.g. for two chemical symbols with concentrations `1/3` and `2/3`, the concentration might look something like `[0.33333333333, 0.66666666666]`. If the client is aware that the sum is not one because of numerical precision, it can renormalize the values so that the sum is exactly one.\n  - Experimental errors in the data present in the database. In this case, it is the responsibility of the client to decide how to process the data.\n\nNote that concentrations are uncorrelated between different sites (even of the same species).",
                        "examples": [
                            [
                                1.0
                            ],
                            [
                                0.3333333333333333,
                                0.2222222222222222,
                                0.4444444444444444
                            ]
                        ],
                        "x-optimade-unit": "inapplicable",
                        "items": {
                            "x-optimade-type": "float",
                            "type": [
                                "number"
                            ],
                            "x-optimade-unit": "dimensionless",
                            "minimum": 0.0,
                            "maximum": 1.0
                        }
                    },
                    "attached": {
                        "title": "Attached chemical symbols",
                        "x-optimade-type": "list",
                        "type": [
                            "array"
                        ],
                        "description": "The chemical symbols of the elements or non-chemical elements attached to a site that has been assinged this species.\n\n**Requirements/Conventions**:\n\n- MUST be a list of strings of all chemical elements composing this species.\n  Each item of the list MUST be one of the following:\n\n  - a valid chemical-element symbol, or\n  - the special value `\"X\"` to represent a non-chemical element, or\n\nIf any one entry in the `species` list has a `attached` list that is longer than 1 element, the correct flag MUST be set in the list `structure_features` (see property `structure_features`).",
                        "examples": [
                            [
                                "Na",
                                "Cl"
                            ],
                            [
                                "Si",
                                "Mn",
                                "X"
                            ]
                        ],
                        "x-optimade-unit": "inapplicable",
                        "items": {
                            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/common/chemical_symbol",
                            "title": "Chemical symbol",
                            "x-optimade-type": "string",
                            "x-optimade-definition": {
                                "kind": "property",
                                "version": "1.2.0",
                                "format": "1.2",
                                "name": "chemical_symbol"
                            },
                            "description": "A chemical symbol refering to an element or a non-chemical element.\n\n**Requirements/Conventions:**\n\n- Must be one of the following:\n\n  - a valid chemical-element symbol, or\n  - the special value `\"X\"` to represent a non-chemical element.",
                            "x-optimade-unit": "inapplicable",
                            "examples": [
                                "He",
                                "X"
                            ],
                            "type": [
                                "string"
                            ],
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
                        }
                    },
                    "nattached": {
                        "title": "Number of attached entities",
                        "x-optimade-type": "list",
                        "type": [
                            "array"
                        ],
                        "description": "MUST be a list of length 1 or more of integers indicating the number of attached atoms of the kind specified in the value of the `attached` key.\n\n**Requirements/Conventions**:\n\n- The implementation MUST include either both or none of the `attached` and `nattached` keys, and if they are provided, they MUST be of the same length.\n  Furthermore, if they are provided, the `structure_features` property MUST include the string `site_attachments`.",
                        "examples": [
                            [
                                1,
                                2,
                                5,
                                7
                            ]
                        ],
                        "x-optimade-unit": "inapplicable",
                        "items": {
                            "x-optimade-type": "integer",
                            "type": [
                                "integer"
                            ],
                            "x-optimade-unit": "dimensionless",
                            "minimum": 0
                        }
                    },
                    "mass": {
                        "title": "Number of attached entities",
                        "x-optimade-type": "list",
                        "type": [
                            "array"
                        ],
                        "description": "MUST be a list of floats, with the same length as `chemical_symbols`, providing element masses expressed in a.m.u.\n\n**Requirements/Conventions**:\n\n- Elements denoting vacancies MUST have masses equal to 0.",
                        "examples": [
                            [
                                58.933195,
                                28.0855
                            ]
                        ],
                        "x-optimade-unit": "inapplicable",
                        "items": {
                            "x-optimade-type": "float",
                            "type": [
                                "number"
                            ],
                            "x-optimade-unit": "dalton",
                            "minimum": 0.0
                        }
                    },
                    "original_name": {
                        "title": "Original name",
                        "x-optimade-type": "string",
                        "type": [
                            "string"
                        ],
                        "description": "A name for the species that derives from the source database.\n\n**Requirements/Conventions**:\n\n- Can be any valid Unicode string, and SHOULD contain (if specified) the name of the species that is used internally in the source database.\n\n  **Note**: With regard to \"source database\", we refer to the immediate source being queried via the OPTIMADE API implementation.\n  The main use of this field is for source databases that use species names, containing characters that are not allowed (see description of the list property `species_at_sites`).",
                        "examples": [
                            "Na[49385]"
                        ],
                        "x-optimade-unit": "inapplicable"
                    }
                },
                "required": [
                    "name",
                    "chemical_symbols",
                    "concentration"
                ]
            }
        },
        "assemblies": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "response-level": "may",
                "query-support": "none"
            },
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
            ]
        },
        "structure_features": {
            "x-optimade-requirements": {
                "support": "must",
                "sortable": false,
                "response-level": "may",
                "query-support": "all mandatory"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/structure/structure_features",
            "title": "Structure features",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "structure_features"
            },
            "description": "A list of strings that flag which special features are used by the structure.\n\n**Requirements/Conventions:**\n\n- MUST be an empty list if no special features are used.\n- MUST be sorted alphabetically.\n- If a special feature listed below is used, the list MUST contain the corresponding string.\n- If a special feature listed below is not used, the list MUST NOT contain the corresponding string.\n- **List of strings used to indicate special structure features:**\n  - `disorder`: this flag MUST be present if any one entry in the species list has a `chemical_symbols` list that is longer than 1 element.\n  - `implicit_atoms`: this flag MUST be present if the structure contains atoms that are not assigned to sites via the property `species_at_sites` (e.g., because their positions are unknown). When this flag is present, the properties related to the chemical formula will likely not match the type and count of atoms represented by the `species_at_sites`, `species`, and `assemblies` properties.\n  - `site_attachments`: this flag MUST be present if any one entry in the species list includes `attached` and `nattached`.\n  - `assemblies`: this flag MUST be present if the property assemblies is present.\n\n  **Explained examples**:\n  - A structure having implicit atoms and using assemblies: `[\"assemblies\", \"implicit_atoms\"]`",
            "examples": [
                [
                    "assemblies",
                    "implicit_atoms"
                ]
            ],
            "x-optimade-type": "list",
            "type": [
                "array"
            ],
            "x-optimade-unit": "inapplicable",
            "items": {
                "type": [
                    "string"
                ],
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable"
            }
        }
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/entrytype_definition.md"
}
```