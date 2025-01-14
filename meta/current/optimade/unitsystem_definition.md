OPTIMADE Unit system definition schema
--------------------------------------


``` json
{
    "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/unitsystem_definition",
    "title": "OPTIMADE Unit system definition schema",
    "type": "object",
    "required": [
        "$id",
        "$schema",
        "x-optimade-definition",
        "title"
    ],
    "properties": {
        "$id": {
            "type": "string"
        },
        "type": {
            "type": [
                "string",
                "array"
            ],
            "enum": [
                "object",
                [
                    "object"
                ]
            ]
        },
        "x-optimade-definition": {
            "properties": {
                "kind": {
                    "const": "unitsystem",
                    "type": "string",
                    "description": "Specifies the kind of Property Definition.",
                    "enum": [
                        "property",
                        "unit",
                        "constant",
                        "prefix",
                        "entrytype",
                        "unitsystem",
                        "standard"
                    ]
                },
                "name": {
                    "type": "string",
                    "description": "Gives the definition a short name.",
                    "pattern": "^[a-z_][a-z_0-9]*$"
                },
                "format": {
                    "description": "Specifies the minor version of the Property Definitions format that the definition is expressed in.\nThis field MUST be included in standalone definitions, i.e., when they are not embedded inside other definitions or contexts that already declares a Property Definitions format.",
                    "pattern": "^[0-9]+\\.[0-9]+$"
                },
                "version": {
                    "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                    "pattern": "^(0|[1-9]\\d*)\\.(0|[1-9]\\d*)\\.(0|[1-9]\\d*)(?:-((?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\\.(?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\\+([0-9a-zA-Z-]+(?:\\.[0-9a-zA-Z-]+)*))?$",
                    "$comment": "This pattern is the suggested regular expression from: https://semver.org/spec/v2.0.0.html",
                    "type": "string"
                },
                "resources": {
                    "type": "array",
                    "description": "A list of dictionaries that reference remote resources that describe the unit.",
                    "items": {
                        "type": "object",
                        "properties": {
                            "relation": {
                                "description": "A human-readable description of the relationship between the unit and the remote resource, e.g., a \"natural language description\".",
                                "type": "string"
                            },
                            "resource-id": {
                                "description": "An IRI of the external resource (which MAY be a resolvable URL).",
                                "format": "iri",
                                "type": "string"
                            }
                        },
                        "required": [
                            "relation",
                            "resource-id"
                        ],
                        "patternProperties": {
                            "^x-": {}
                        },
                        "additionalProperties": false
                    }
                }
            },
            "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/x-optimade-definition-field",
            "type": "object",
            "required": [
                "kind",
                "format",
                "name"
            ],
            "patternProperties": {
                "^x-": {}
            },
            "additionalProperties": false
        },
        "title": {
            "type": "string"
        },
        "description": {
            "type": "string"
        },
        "units": {
            "type": "object",
            "additionalProperties": {
                "required": [
                    "title",
                    "description",
                    "x-optimade-definition"
                ],
                "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition",
                "title": "OPTIMADE Physical Unit Definition",
                "type": "object",
                "additionalProperties": false,
                "patternProperties": {
                    "^_": {}
                },
                "properties": {
                    "$id": {
                        "description": "A static IRI identifier that is a URN or URL representing the specific version of the Physical Unit Definition.\n\n(If it is a URL, clients SHOULD NOT assign any interpretation to the response when resolving that URL.)\nIt SHOULD NOT be changed as long as the Physical Unit Definition remains the same, and SHOULD be changed when the definition changes.\nPhysical Unit Definitions SHOULD be regarded as the same if they only differ by:\n- Additions of annotating notes to end of the `description` field.\n- Changes to the following specific fields at any level: `deprecated` and `$comment`.",
                        "type": "string"
                    },
                    "$comment": {
                        "type": "string"
                    },
                    "approximate-relations": {
                        "items": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "properties": {
                                "base-units": {
                                    "items": {
                                        "properties": {
                                            "id": {
                                                "format": "uri",
                                                "type": "string"
                                            },
                                            "symbol": {
                                                "type": "string"
                                            }
                                        },
                                        "required": [
                                            "symbol",
                                            "id"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "base-units-expression": {
                                    "type": "string"
                                },
                                "offset": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "relative_standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "value": {
                                            "type": "number"
                                        }
                                    },
                                    "required": [
                                        "value"
                                    ],
                                    "type": "object"
                                },
                                "scale": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "relative_standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "value": {
                                            "type": "number"
                                        }
                                    },
                                    "required": [
                                        "value"
                                    ],
                                    "type": "object"
                                }
                            },
                            "type": "object"
                        },
                        "type": "array"
                    },
                    "compatibility": {
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "defining-relation": {
                        "description": "A dictionary that encodes a defining relation to another unit or set of units, with the primary intended use of relating a unit to its definition in SI units, if such a relationship exists.\nSome units, e.g., the atomic mass unit (also known as dalton, commonly denoted `u`), only has an approximate relationship to SI units, in which case the `defining-relation` MUST be omitted or `null`.\n\nIf the fields in `scale` are designated as `sn`, `sd`, and `se`; and the fields in `offset` are designated as `on`, `od`, and `oe`; and `base-units-expression` is designated as `b`, these fields state the following defining relation: a value `v` multiplied by the unit being defined is equal to the following expression `(v * (sn/sd) * 10**se + (on/od) * 10**oe)*b`, where `*` designates multiplication and `**` designates exponentiation.",
                        "properties": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "base-units": {
                                "items": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "id": {
                                            "description": "The IRI of one of the units referenced in the dimensional formula for the defining relation.",
                                            "format": "uri",
                                            "type": "string"
                                        },
                                        "symbol": {
                                            "description": "The symbol used to reference this unit in the dimensional formula.",
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "symbol",
                                        "id"
                                    ],
                                    "type": "object"
                                },
                                "type": "array"
                            },
                            "base-units-expression": {
                                "description": "A string expressing the base units part of the defining relation for the unit being defined.\n\nA compound unit expression is created by a sequence of constants, prefixes, and unit symbols separated by a single multiplication `*` symbol.\nEach unit symbol can also be suffixed by a single `^` symbol followed by a positive or negative integer to indicate the power of the preceding unit, e.g., `m^3` for cubic meter, `m^-3` for inverse cubic meter.\n(Positive integers MUST NOT be preceded by a plus sign.)\nFurthermore:\n\n- No whitespace, parenthesis, or other symbols than specified above are permitted.\n- The unit symbols MUST appear in alphabetical order.",
                                "type": "string"
                            },
                            "scale": {
                                "description": "A dictionary specifying the scale in the defining relation.\n\nThe four fields `numerator`, `denominator`, `base`, and `exponent` specify the value as the rational number `numerator` / `denominator`, multiplied by `base` to the power of `exponent`.\nIf omitted or `null`, the defaults for the `numerator`, `denominator`, `base` and `exponent` are respectively 1, 1, 10, and 0.",
                                "patternProperties": {
                                    "^_": {}
                                },
                                "properties": {
                                    "denominator": {
                                        "type": "integer"
                                    },
                                    "numerator": {
                                        "type": "integer"
                                    },
                                    "exponent": {
                                        "type": "integer"
                                    },
                                    "base": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            },
                            "offset": {
                                "description": "The four fields `numerator`, `denominator`, `base`, and `exponent` specify the value as the rational number `numerator` / `denominator`, multiplied by `base` to the power of `exponent`.\nIf omitted or `null`, the defaults for the `numerator`, `denominator`, `base` and `exponent` are respectively 0, 1, 10, and 0.",
                                "patternProperties": {
                                    "^_": {}
                                },
                                "properties": {
                                    "denominator": {
                                        "type": "integer"
                                    },
                                    "exponent": {
                                        "type": "integer"
                                    },
                                    "numerator": {
                                        "type": "integer"
                                    },
                                    "base": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            }
                        },
                        "type": "object"
                    },
                    "description": {
                        "description": "A human-readable multiple-line detailed description of the unit.\n\nAdditions appended to the end of the `description` field that are clearly marked as notes that clarify the definition without changing it are viewed as annotations to the Physical Unit Definition rather than an integral part of it.\nSuch annotations SHOULD only be added to the end of an otherwise unmodified `description` and MUST NOT change the meaning or interpretation of the text above them.\nThe purpose is to provide a way to add explanations and clarifications to a definition without having to regard it as a new definition.\nFor example, these annotations to the description MAY be used to explain why a definition has been deprecated.",
                        "type": "string"
                    },
                    "resources": {
                        "description": "A list of dictionaries that reference remote resources that describe the unit.",
                        "items": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "properties": {
                                "relation": {
                                    "description": "A human-readable description of the relationship between the unit and the remote resource.",
                                    "type": "string"
                                },
                                "resource-id": {
                                    "description": "A IRI of the external resource (which MAY be a resolvable URL).",
                                    "type": "string"
                                }
                            },
                            "required": [
                                "relation",
                                "resource-id"
                            ],
                            "type": "object"
                        },
                        "type": "array"
                    },
                    "standard": {
                        "description": "This field is used to define the unit symbol using a preexisting standard.",
                        "patternProperties": {
                            "^_": {}
                        },
                        "properties": {
                            "name": {
                                "description": "The abbreviated name of the standard being referenced.",
                                "enum": [
                                    "gnu units",
                                    "ucum",
                                    "qudt"
                                ],
                                "type": "string"
                            },
                            "symbol": {
                                "description": "The symbol to use from the referenced standard, expressed according to that standard.\nThis field MAY be different from `symbol` directly under `unit-definitions`, meaning that the unit is referenced in `x-optimade-unit` fields using a different symbol than the one used in the standard.\nHowever, the `symbol` fields SHOULD be the same unless multiple units sharing the same symbol need to be referenced.",
                                "type": "string"
                            },
                            "version": {
                                "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                                "type": "string"
                            }
                        },
                        "required": [
                            "name",
                            "version",
                            "symbol"
                        ],
                        "type": "object"
                    },
                    "symbol": {
                        "description": "Specifies the symbol to be used in `x-optimade-unit` to reference this unit.",
                        "type": "string",
                        "pattern": "^[a-zA-Z_][a-zA-Z_0-9]*$"
                    },
                    "display-symbol": {
                        "description": "The suggested standard typographical symbolic representation of the unit.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2.",
                        "type": "string"
                    },
                    "alternate-symbols": {
                        "description": "A list of other symbols often used for the unit.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2.",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "title": {
                        "description": "The standard human-readable name of the unit.",
                        "type": "string"
                    },
                    "x-optimade-definition": {
                        "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/x-optimade-definition-field",
                        "type": "object",
                        "required": [
                            "kind",
                            "format",
                            "name"
                        ],
                        "properties": {
                            "name": {
                                "type": "string",
                                "description": "Gives the definition a short name.",
                                "pattern": "^[a-z_][a-z_0-9]*$"
                            },
                            "kind": {
                                "type": "string",
                                "description": "Specifies the kind of Property Definition.",
                                "enum": [
                                    "property",
                                    "unit",
                                    "constant",
                                    "prefix",
                                    "entrytype",
                                    "unitsystem",
                                    "standard"
                                ]
                            },
                            "format": {
                                "description": "Specifies the minor version of the Property Definitions format that the definition is expressed in.\nThis field MUST be included in standalone definitions, i.e., when they are not embedded inside other definitions or contexts that already declares a Property Definitions format.",
                                "pattern": "^[0-9]+\\.[0-9]+$"
                            },
                            "version": {
                                "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                                "pattern": "^(0|[1-9]\\d*)\\.(0|[1-9]\\d*)\\.(0|[1-9]\\d*)(?:-((?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\\.(?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\\+([0-9a-zA-Z-]+(?:\\.[0-9a-zA-Z-]+)*))?$",
                                "$comment": "This pattern is the suggested regular expression from: https://semver.org/spec/v2.0.0.html",
                                "type": "string"
                            },
                            "resources": {
                                "type": "array",
                                "description": "A list of dictionaries that reference remote resources that describe the unit.",
                                "items": {
                                    "type": "object",
                                    "properties": {
                                        "relation": {
                                            "description": "A human-readable description of the relationship between the unit and the remote resource, e.g., a \"natural language description\".",
                                            "type": "string"
                                        },
                                        "resource-id": {
                                            "description": "An IRI of the external resource (which MAY be a resolvable URL).",
                                            "format": "iri",
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "relation",
                                        "resource-id"
                                    ],
                                    "patternProperties": {
                                        "^x-": {}
                                    },
                                    "additionalProperties": false
                                }
                            }
                        },
                        "patternProperties": {
                            "^x-": {}
                        },
                        "additionalProperties": false
                    }
                }
            }
        },
        "constants": {
            "type": "object",
            "additionalProperties": {
                "required": [
                    "title",
                    "description",
                    "x-optimade-definition"
                ],
                "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition",
                "title": "OPTIMADE Physical Unit Definition",
                "type": "object",
                "additionalProperties": false,
                "patternProperties": {
                    "^_": {}
                },
                "properties": {
                    "$id": {
                        "description": "A static IRI identifier that is a URN or URL representing the specific version of the Physical Unit Definition.\n\n(If it is a URL, clients SHOULD NOT assign any interpretation to the response when resolving that URL.)\nIt SHOULD NOT be changed as long as the Physical Unit Definition remains the same, and SHOULD be changed when the definition changes.\nPhysical Unit Definitions SHOULD be regarded as the same if they only differ by:\n- Additions of annotating notes to end of the `description` field.\n- Changes to the following specific fields at any level: `deprecated` and `$comment`.",
                        "type": "string"
                    },
                    "$comment": {
                        "type": "string"
                    },
                    "approximate-relations": {
                        "items": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "properties": {
                                "base-units": {
                                    "items": {
                                        "properties": {
                                            "id": {
                                                "format": "uri",
                                                "type": "string"
                                            },
                                            "symbol": {
                                                "type": "string"
                                            }
                                        },
                                        "required": [
                                            "symbol",
                                            "id"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "base-units-expression": {
                                    "type": "string"
                                },
                                "offset": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "relative_standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "value": {
                                            "type": "number"
                                        }
                                    },
                                    "required": [
                                        "value"
                                    ],
                                    "type": "object"
                                },
                                "scale": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "relative_standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "value": {
                                            "type": "number"
                                        }
                                    },
                                    "required": [
                                        "value"
                                    ],
                                    "type": "object"
                                }
                            },
                            "type": "object"
                        },
                        "type": "array"
                    },
                    "compatibility": {
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "defining-relation": {
                        "description": "A dictionary that encodes a defining relation to another unit or set of units, with the primary intended use of relating a unit to its definition in SI units, if such a relationship exists.\nSome units, e.g., the atomic mass unit (also known as dalton, commonly denoted `u`), only has an approximate relationship to SI units, in which case the `defining-relation` MUST be omitted or `null`.\n\nIf the fields in `scale` are designated as `sn`, `sd`, and `se`; and the fields in `offset` are designated as `on`, `od`, and `oe`; and `base-units-expression` is designated as `b`, these fields state the following defining relation: a value `v` multiplied by the unit being defined is equal to the following expression `(v * (sn/sd) * 10**se + (on/od) * 10**oe)*b`, where `*` designates multiplication and `**` designates exponentiation.",
                        "properties": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "base-units": {
                                "items": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "id": {
                                            "description": "The IRI of one of the units referenced in the dimensional formula for the defining relation.",
                                            "format": "uri",
                                            "type": "string"
                                        },
                                        "symbol": {
                                            "description": "The symbol used to reference this unit in the dimensional formula.",
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "symbol",
                                        "id"
                                    ],
                                    "type": "object"
                                },
                                "type": "array"
                            },
                            "base-units-expression": {
                                "description": "A string expressing the base units part of the defining relation for the unit being defined.\n\nA compound unit expression is created by a sequence of constants, prefixes, and unit symbols separated by a single multiplication `*` symbol.\nEach unit symbol can also be suffixed by a single `^` symbol followed by a positive or negative integer to indicate the power of the preceding unit, e.g., `m^3` for cubic meter, `m^-3` for inverse cubic meter.\n(Positive integers MUST NOT be preceded by a plus sign.)\nFurthermore:\n\n- No whitespace, parenthesis, or other symbols than specified above are permitted.\n- The unit symbols MUST appear in alphabetical order.",
                                "type": "string"
                            },
                            "scale": {
                                "description": "A dictionary specifying the scale in the defining relation.\n\nThe four fields `numerator`, `denominator`, `base`, and `exponent` specify the value as the rational number `numerator` / `denominator`, multiplied by `base` to the power of `exponent`.\nIf omitted or `null`, the defaults for the `numerator`, `denominator`, `base` and `exponent` are respectively 1, 1, 10, and 0.",
                                "patternProperties": {
                                    "^_": {}
                                },
                                "properties": {
                                    "denominator": {
                                        "type": "integer"
                                    },
                                    "numerator": {
                                        "type": "integer"
                                    },
                                    "exponent": {
                                        "type": "integer"
                                    },
                                    "base": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            },
                            "offset": {
                                "description": "The four fields `numerator`, `denominator`, `base`, and `exponent` specify the value as the rational number `numerator` / `denominator`, multiplied by `base` to the power of `exponent`.\nIf omitted or `null`, the defaults for the `numerator`, `denominator`, `base` and `exponent` are respectively 0, 1, 10, and 0.",
                                "patternProperties": {
                                    "^_": {}
                                },
                                "properties": {
                                    "denominator": {
                                        "type": "integer"
                                    },
                                    "exponent": {
                                        "type": "integer"
                                    },
                                    "numerator": {
                                        "type": "integer"
                                    },
                                    "base": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            }
                        },
                        "type": "object"
                    },
                    "description": {
                        "description": "A human-readable multiple-line detailed description of the unit.\n\nAdditions appended to the end of the `description` field that are clearly marked as notes that clarify the definition without changing it are viewed as annotations to the Physical Unit Definition rather than an integral part of it.\nSuch annotations SHOULD only be added to the end of an otherwise unmodified `description` and MUST NOT change the meaning or interpretation of the text above them.\nThe purpose is to provide a way to add explanations and clarifications to a definition without having to regard it as a new definition.\nFor example, these annotations to the description MAY be used to explain why a definition has been deprecated.",
                        "type": "string"
                    },
                    "resources": {
                        "description": "A list of dictionaries that reference remote resources that describe the unit.",
                        "items": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "properties": {
                                "relation": {
                                    "description": "A human-readable description of the relationship between the unit and the remote resource.",
                                    "type": "string"
                                },
                                "resource-id": {
                                    "description": "A IRI of the external resource (which MAY be a resolvable URL).",
                                    "type": "string"
                                }
                            },
                            "required": [
                                "relation",
                                "resource-id"
                            ],
                            "type": "object"
                        },
                        "type": "array"
                    },
                    "standard": {
                        "description": "This field is used to define the unit symbol using a preexisting standard.",
                        "patternProperties": {
                            "^_": {}
                        },
                        "properties": {
                            "name": {
                                "description": "The abbreviated name of the standard being referenced.",
                                "enum": [
                                    "gnu units",
                                    "ucum",
                                    "qudt"
                                ],
                                "type": "string"
                            },
                            "symbol": {
                                "description": "The symbol to use from the referenced standard, expressed according to that standard.\nThis field MAY be different from `symbol` directly under `unit-definitions`, meaning that the unit is referenced in `x-optimade-unit` fields using a different symbol than the one used in the standard.\nHowever, the `symbol` fields SHOULD be the same unless multiple units sharing the same symbol need to be referenced.",
                                "type": "string"
                            },
                            "version": {
                                "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                                "type": "string"
                            }
                        },
                        "required": [
                            "name",
                            "version",
                            "symbol"
                        ],
                        "type": "object"
                    },
                    "symbol": {
                        "description": "Specifies the symbol to be used in `x-optimade-unit` to reference this unit.",
                        "type": "string",
                        "pattern": "^[a-zA-Z_][a-zA-Z_0-9]*$"
                    },
                    "display-symbol": {
                        "description": "The suggested standard typographical symbolic representation of the unit.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2.",
                        "type": "string"
                    },
                    "alternate-symbols": {
                        "description": "A list of other symbols often used for the unit.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2.",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "title": {
                        "description": "The standard human-readable name of the unit.",
                        "type": "string"
                    },
                    "x-optimade-definition": {
                        "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/x-optimade-definition-field",
                        "type": "object",
                        "required": [
                            "kind",
                            "format",
                            "name"
                        ],
                        "properties": {
                            "name": {
                                "type": "string",
                                "description": "Gives the definition a short name.",
                                "pattern": "^[a-z_][a-z_0-9]*$"
                            },
                            "kind": {
                                "type": "string",
                                "description": "Specifies the kind of Property Definition.",
                                "enum": [
                                    "property",
                                    "unit",
                                    "constant",
                                    "prefix",
                                    "entrytype",
                                    "unitsystem",
                                    "standard"
                                ]
                            },
                            "format": {
                                "description": "Specifies the minor version of the Property Definitions format that the definition is expressed in.\nThis field MUST be included in standalone definitions, i.e., when they are not embedded inside other definitions or contexts that already declares a Property Definitions format.",
                                "pattern": "^[0-9]+\\.[0-9]+$"
                            },
                            "version": {
                                "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                                "pattern": "^(0|[1-9]\\d*)\\.(0|[1-9]\\d*)\\.(0|[1-9]\\d*)(?:-((?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\\.(?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\\+([0-9a-zA-Z-]+(?:\\.[0-9a-zA-Z-]+)*))?$",
                                "$comment": "This pattern is the suggested regular expression from: https://semver.org/spec/v2.0.0.html",
                                "type": "string"
                            },
                            "resources": {
                                "type": "array",
                                "description": "A list of dictionaries that reference remote resources that describe the unit.",
                                "items": {
                                    "type": "object",
                                    "properties": {
                                        "relation": {
                                            "description": "A human-readable description of the relationship between the unit and the remote resource, e.g., a \"natural language description\".",
                                            "type": "string"
                                        },
                                        "resource-id": {
                                            "description": "An IRI of the external resource (which MAY be a resolvable URL).",
                                            "format": "iri",
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "relation",
                                        "resource-id"
                                    ],
                                    "patternProperties": {
                                        "^x-": {}
                                    },
                                    "additionalProperties": false
                                }
                            }
                        },
                        "patternProperties": {
                            "^x-": {}
                        },
                        "additionalProperties": false
                    }
                }
            }
        },
        "prefixes": {
            "type": "object",
            "additionalProperties": {
                "required": [
                    "title",
                    "description",
                    "x-optimade-definition"
                ],
                "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition",
                "title": "OPTIMADE Physical Unit Definition",
                "type": "object",
                "additionalProperties": false,
                "patternProperties": {
                    "^_": {}
                },
                "properties": {
                    "$id": {
                        "description": "A static IRI identifier that is a URN or URL representing the specific version of the Physical Unit Definition.\n\n(If it is a URL, clients SHOULD NOT assign any interpretation to the response when resolving that URL.)\nIt SHOULD NOT be changed as long as the Physical Unit Definition remains the same, and SHOULD be changed when the definition changes.\nPhysical Unit Definitions SHOULD be regarded as the same if they only differ by:\n- Additions of annotating notes to end of the `description` field.\n- Changes to the following specific fields at any level: `deprecated` and `$comment`.",
                        "type": "string"
                    },
                    "$comment": {
                        "type": "string"
                    },
                    "approximate-relations": {
                        "items": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "properties": {
                                "base-units": {
                                    "items": {
                                        "properties": {
                                            "id": {
                                                "format": "uri",
                                                "type": "string"
                                            },
                                            "symbol": {
                                                "type": "string"
                                            }
                                        },
                                        "required": [
                                            "symbol",
                                            "id"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "base-units-expression": {
                                    "type": "string"
                                },
                                "offset": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "relative_standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "value": {
                                            "type": "number"
                                        }
                                    },
                                    "required": [
                                        "value"
                                    ],
                                    "type": "object"
                                },
                                "scale": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "relative_standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "standard_uncertainty": {
                                            "type": "number"
                                        },
                                        "value": {
                                            "type": "number"
                                        }
                                    },
                                    "required": [
                                        "value"
                                    ],
                                    "type": "object"
                                }
                            },
                            "type": "object"
                        },
                        "type": "array"
                    },
                    "compatibility": {
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "defining-relation": {
                        "description": "A dictionary that encodes a defining relation to another unit or set of units, with the primary intended use of relating a unit to its definition in SI units, if such a relationship exists.\nSome units, e.g., the atomic mass unit (also known as dalton, commonly denoted `u`), only has an approximate relationship to SI units, in which case the `defining-relation` MUST be omitted or `null`.\n\nIf the fields in `scale` are designated as `sn`, `sd`, and `se`; and the fields in `offset` are designated as `on`, `od`, and `oe`; and `base-units-expression` is designated as `b`, these fields state the following defining relation: a value `v` multiplied by the unit being defined is equal to the following expression `(v * (sn/sd) * 10**se + (on/od) * 10**oe)*b`, where `*` designates multiplication and `**` designates exponentiation.",
                        "properties": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "base-units": {
                                "items": {
                                    "patternProperties": {
                                        "^_": {}
                                    },
                                    "properties": {
                                        "id": {
                                            "description": "The IRI of one of the units referenced in the dimensional formula for the defining relation.",
                                            "format": "uri",
                                            "type": "string"
                                        },
                                        "symbol": {
                                            "description": "The symbol used to reference this unit in the dimensional formula.",
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "symbol",
                                        "id"
                                    ],
                                    "type": "object"
                                },
                                "type": "array"
                            },
                            "base-units-expression": {
                                "description": "A string expressing the base units part of the defining relation for the unit being defined.\n\nA compound unit expression is created by a sequence of constants, prefixes, and unit symbols separated by a single multiplication `*` symbol.\nEach unit symbol can also be suffixed by a single `^` symbol followed by a positive or negative integer to indicate the power of the preceding unit, e.g., `m^3` for cubic meter, `m^-3` for inverse cubic meter.\n(Positive integers MUST NOT be preceded by a plus sign.)\nFurthermore:\n\n- No whitespace, parenthesis, or other symbols than specified above are permitted.\n- The unit symbols MUST appear in alphabetical order.",
                                "type": "string"
                            },
                            "scale": {
                                "description": "A dictionary specifying the scale in the defining relation.\n\nThe four fields `numerator`, `denominator`, `base`, and `exponent` specify the value as the rational number `numerator` / `denominator`, multiplied by `base` to the power of `exponent`.\nIf omitted or `null`, the defaults for the `numerator`, `denominator`, `base` and `exponent` are respectively 1, 1, 10, and 0.",
                                "patternProperties": {
                                    "^_": {}
                                },
                                "properties": {
                                    "denominator": {
                                        "type": "integer"
                                    },
                                    "numerator": {
                                        "type": "integer"
                                    },
                                    "exponent": {
                                        "type": "integer"
                                    },
                                    "base": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            },
                            "offset": {
                                "description": "The four fields `numerator`, `denominator`, `base`, and `exponent` specify the value as the rational number `numerator` / `denominator`, multiplied by `base` to the power of `exponent`.\nIf omitted or `null`, the defaults for the `numerator`, `denominator`, `base` and `exponent` are respectively 0, 1, 10, and 0.",
                                "patternProperties": {
                                    "^_": {}
                                },
                                "properties": {
                                    "denominator": {
                                        "type": "integer"
                                    },
                                    "exponent": {
                                        "type": "integer"
                                    },
                                    "numerator": {
                                        "type": "integer"
                                    },
                                    "base": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            }
                        },
                        "type": "object"
                    },
                    "description": {
                        "description": "A human-readable multiple-line detailed description of the unit.\n\nAdditions appended to the end of the `description` field that are clearly marked as notes that clarify the definition without changing it are viewed as annotations to the Physical Unit Definition rather than an integral part of it.\nSuch annotations SHOULD only be added to the end of an otherwise unmodified `description` and MUST NOT change the meaning or interpretation of the text above them.\nThe purpose is to provide a way to add explanations and clarifications to a definition without having to regard it as a new definition.\nFor example, these annotations to the description MAY be used to explain why a definition has been deprecated.",
                        "type": "string"
                    },
                    "resources": {
                        "description": "A list of dictionaries that reference remote resources that describe the unit.",
                        "items": {
                            "patternProperties": {
                                "^_": {}
                            },
                            "properties": {
                                "relation": {
                                    "description": "A human-readable description of the relationship between the unit and the remote resource.",
                                    "type": "string"
                                },
                                "resource-id": {
                                    "description": "A IRI of the external resource (which MAY be a resolvable URL).",
                                    "type": "string"
                                }
                            },
                            "required": [
                                "relation",
                                "resource-id"
                            ],
                            "type": "object"
                        },
                        "type": "array"
                    },
                    "standard": {
                        "description": "This field is used to define the unit symbol using a preexisting standard.",
                        "patternProperties": {
                            "^_": {}
                        },
                        "properties": {
                            "name": {
                                "description": "The abbreviated name of the standard being referenced.",
                                "enum": [
                                    "gnu units",
                                    "ucum",
                                    "qudt"
                                ],
                                "type": "string"
                            },
                            "symbol": {
                                "description": "The symbol to use from the referenced standard, expressed according to that standard.\nThis field MAY be different from `symbol` directly under `unit-definitions`, meaning that the unit is referenced in `x-optimade-unit` fields using a different symbol than the one used in the standard.\nHowever, the `symbol` fields SHOULD be the same unless multiple units sharing the same symbol need to be referenced.",
                                "type": "string"
                            },
                            "version": {
                                "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                                "type": "string"
                            }
                        },
                        "required": [
                            "name",
                            "version",
                            "symbol"
                        ],
                        "type": "object"
                    },
                    "symbol": {
                        "description": "Specifies the symbol to be used in `x-optimade-unit` to reference this unit.",
                        "type": "string",
                        "pattern": "^[a-zA-Z_][a-zA-Z_0-9]*$"
                    },
                    "display-symbol": {
                        "description": "The suggested standard typographical symbolic representation of the unit.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2.",
                        "type": "string"
                    },
                    "alternate-symbols": {
                        "description": "A list of other symbols often used for the unit.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2.",
                        "type": "array",
                        "items": {
                            "type": "string"
                        }
                    },
                    "title": {
                        "description": "The standard human-readable name of the unit.",
                        "type": "string"
                    },
                    "x-optimade-definition": {
                        "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/x-optimade-definition-field",
                        "type": "object",
                        "required": [
                            "kind",
                            "format",
                            "name"
                        ],
                        "properties": {
                            "name": {
                                "type": "string",
                                "description": "Gives the definition a short name.",
                                "pattern": "^[a-z_][a-z_0-9]*$"
                            },
                            "kind": {
                                "type": "string",
                                "description": "Specifies the kind of Property Definition.",
                                "enum": [
                                    "property",
                                    "unit",
                                    "constant",
                                    "prefix",
                                    "entrytype",
                                    "unitsystem",
                                    "standard"
                                ]
                            },
                            "format": {
                                "description": "Specifies the minor version of the Property Definitions format that the definition is expressed in.\nThis field MUST be included in standalone definitions, i.e., when they are not embedded inside other definitions or contexts that already declares a Property Definitions format.",
                                "pattern": "^[0-9]+\\.[0-9]+$"
                            },
                            "version": {
                                "description": "The version string of the referenced standard.\nThe string SHOULD be in the format described by the [semantic versioning v2](https://semver.org/spec/v2.0.0.html) standard.",
                                "pattern": "^(0|[1-9]\\d*)\\.(0|[1-9]\\d*)\\.(0|[1-9]\\d*)(?:-((?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\\.(?:0|[1-9]\\d*|\\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\\+([0-9a-zA-Z-]+(?:\\.[0-9a-zA-Z-]+)*))?$",
                                "$comment": "This pattern is the suggested regular expression from: https://semver.org/spec/v2.0.0.html",
                                "type": "string"
                            },
                            "resources": {
                                "type": "array",
                                "description": "A list of dictionaries that reference remote resources that describe the unit.",
                                "items": {
                                    "type": "object",
                                    "properties": {
                                        "relation": {
                                            "description": "A human-readable description of the relationship between the unit and the remote resource, e.g., a \"natural language description\".",
                                            "type": "string"
                                        },
                                        "resource-id": {
                                            "description": "An IRI of the external resource (which MAY be a resolvable URL).",
                                            "format": "iri",
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "relation",
                                        "resource-id"
                                    ],
                                    "patternProperties": {
                                        "^x-": {}
                                    },
                                    "additionalProperties": false
                                }
                            }
                        },
                        "patternProperties": {
                            "^x-": {}
                        },
                        "additionalProperties": false
                    }
                }
            }
        }
    },
    "additionalProperties": false,
    "$schema": "https://json-schema.org/draft/2020-12/schema.md"
}
```