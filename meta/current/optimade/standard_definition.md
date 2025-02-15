OPTIMADE Endpoint Definition schema
-----------------------------------


``` json
{
    "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/standard_definition",
    "$schema": "https://json-schema.org/draft/2020-12/schema",
    "title": "OPTIMADE Endpoint Definition schema",
    "type": "object",
    "required": [
        "$id",
        "$schema",
        "x-optimade-definition",
        "title",
        "entrytypes"
    ],
    "properties": {
        "$id": {
            "type": "string"
        },
        "title": {
            "type": "string"
        },
        "description": {
            "type": "string"
        },
        "x-optimade-definition": {
            "properties": {
                "kind": {
                    "const": "standard",
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
        "entrytypes": {
            "type": "object",
            "additionalProperties": {
                "required": [
                    "title",
                    "type",
                    "x-optimade-definition",
                    "properties"
                ],
                "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/entrytype_definition",
                "title": "OPTIMADE Node type definition schema",
                "type": "object",
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
                                "const": "entrytype",
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
                    "x-optimade-requirements": {
                        "properties": {
                            "support": {
                                "type": "string"
                            }
                        }
                    },
                    "title": {
                        "type": "string"
                    },
                    "description": {
                        "type": "string"
                    },
                    "properties": {
                        "type": "object",
                        "additionalProperties": {
                            "required": [
                                "title",
                                "description",
                                "x-optimade-definition"
                            ],
                            "$id": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition",
                            "title": "OPTIMADE Property Definition schema",
                            "type": "object",
                            "$ref": "#/$defs/propdef",
                            "$defs": {
                                "propdef": {
                                    "required": [
                                        "type",
                                        "x-optimade-type",
                                        "x-optimade-unit"
                                    ],
                                    "anyOf": [
                                        {
                                            "type": "object",
                                            "required": [
                                                "properties"
                                            ],
                                            "properties": {
                                                "type": {
                                                    "enum": [
                                                        [
                                                            "object"
                                                        ],
                                                        [
                                                            "object",
                                                            "null"
                                                        ]
                                                    ]
                                                },
                                                "enum": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "object"
                                                    }
                                                },
                                                "examples": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "object"
                                                    }
                                                }
                                            }
                                        },
                                        {
                                            "type": "object",
                                            "required": [
                                                "type",
                                                "items"
                                            ],
                                            "properties": {
                                                "type": {
                                                    "enum": [
                                                        [
                                                            "array"
                                                        ],
                                                        [
                                                            "array",
                                                            "null"
                                                        ]
                                                    ]
                                                },
                                                "enum": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "array"
                                                    }
                                                },
                                                "examples": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "array"
                                                    }
                                                }
                                            }
                                        },
                                        {
                                            "type": "object",
                                            "required": [
                                                "type"
                                            ],
                                            "properties": {
                                                "type": {
                                                    "enum": [
                                                        [
                                                            "integer"
                                                        ],
                                                        [
                                                            "integer",
                                                            "null"
                                                        ]
                                                    ]
                                                },
                                                "multipleOf": {
                                                    "type": "integer"
                                                },
                                                "maximum": {
                                                    "type": "integer"
                                                },
                                                "exclusiveMaximum": {
                                                    "type": "integer"
                                                },
                                                "minimum": {
                                                    "type": "integer"
                                                },
                                                "exclusiveMinimum": {
                                                    "type": "integer"
                                                },
                                                "enum": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "integer"
                                                    }
                                                },
                                                "examples": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "integer"
                                                    }
                                                }
                                            }
                                        },
                                        {
                                            "type": "object",
                                            "required": [
                                                "type"
                                            ],
                                            "properties": {
                                                "type": {
                                                    "enum": [
                                                        [
                                                            "number"
                                                        ],
                                                        [
                                                            "number",
                                                            "null"
                                                        ]
                                                    ]
                                                },
                                                "multipleOf": {
                                                    "type": "number"
                                                },
                                                "maximum": {
                                                    "type": "number"
                                                },
                                                "exclusiveMaximum": {
                                                    "type": "number"
                                                },
                                                "minimum": {
                                                    "type": "number"
                                                },
                                                "exclusiveMinimum": {
                                                    "type": "number"
                                                },
                                                "enum": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "number"
                                                    }
                                                },
                                                "examples": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "number"
                                                    }
                                                }
                                            }
                                        },
                                        {
                                            "type": "object",
                                            "required": [
                                                "type"
                                            ],
                                            "properties": {
                                                "type": {
                                                    "enum": [
                                                        [
                                                            "string"
                                                        ],
                                                        [
                                                            "string",
                                                            "null"
                                                        ]
                                                    ]
                                                },
                                                "enum": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "string"
                                                    }
                                                },
                                                "examples": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "string"
                                                    }
                                                }
                                            }
                                        },
                                        {
                                            "type": "object",
                                            "required": [
                                                "type"
                                            ],
                                            "properties": {
                                                "type": {
                                                    "enum": [
                                                        [
                                                            "boolean"
                                                        ],
                                                        [
                                                            "boolean",
                                                            "null"
                                                        ]
                                                    ]
                                                },
                                                "enum": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "examples": {
                                                    "type": "array",
                                                    "items": {
                                                        "type": "boolean"
                                                    }
                                                }
                                            }
                                        }
                                    ],
                                    "properties": {
                                        "type": {
                                            "description": "Specifies the corresponding JSON type for this level of the defined property and whether the property can be `null` or not.\nThe value is directly correlated with `x-optimade-type` (cf. the `definition of the x-optimade-type field`).\n\nIt MUST be a list of one or two elements where the first element is a string correlated with `x-optimade-type` as follows; if `x-optimade-type` is:\n* `\"boolean\"`, `\"string\"`, or `\"integer\"` then `type` is the same string.\n* `\"dictionary\"` then `type` is `\"object\"`.\n* `\"list\"` then `type` is `\"array\"`.\n* `\"float\"` then `type` is `\"number\"`.\n* `\"timestamp\"` then `type` is `\"string\"`.\n\nIf the second element is included, it MUST be the string `\"null\"`.\nThis two element form specifies that the defined property can be `null`.",
                                            "type": "array",
                                            "enum": [
                                                [
                                                    "object"
                                                ],
                                                [
                                                    "object",
                                                    "null"
                                                ],
                                                [
                                                    "array"
                                                ],
                                                [
                                                    "array",
                                                    "null"
                                                ],
                                                [
                                                    "integer"
                                                ],
                                                [
                                                    "integer",
                                                    "null"
                                                ],
                                                [
                                                    "number"
                                                ],
                                                [
                                                    "number",
                                                    "null"
                                                ],
                                                [
                                                    "string"
                                                ],
                                                [
                                                    "string",
                                                    "null"
                                                ],
                                                [
                                                    "boolean"
                                                ],
                                                [
                                                    "boolean",
                                                    "null"
                                                ]
                                            ],
                                            "items": {
                                                "type": "string"
                                            }
                                        },
                                        "properties": {
                                            "description": "Gives key-value pairs where each value is an inner Property Definition.\nThe defined property is a dictionary that can only contain keys present in this dictionary, and, if so, the corresponding value is described by the respective inner Property Definition.\n(Or, if the type field is the list \"object\" and \"null\", it can also be null.)",
                                            "type": "object",
                                            "additionalProperties": {
                                                "$ref": "#/$defs/propdef"
                                            }
                                        },
                                        "required": {
                                            "description": "The defined property MUST have keys that match all the strings in this list.\nOther keys present in the properties field are OPTIONAL in the defined property.\nIf not present or empty, all keys in properties are regarded as OPTIONAL.",
                                            "type": "array",
                                            "items": {
                                                "type": "string"
                                            },
                                            "uniqueItems": true
                                        },
                                        "maxProperties": {
                                            "description": "The defined property is a dictionary where the number of keys MUST be less than or equal to the number given.",
                                            "type": "integer",
                                            "minimum": 0
                                        },
                                        "minProperties": {
                                            "description": "The defined property is a dictionary where the number of keys MUST be greater than or equal to the number given.",
                                            "type": "integer",
                                            "minimum": 0
                                        },
                                        "dependentRequired": {
                                            "description": "The dictionary keys are strings and the values are lists of unique strings.\nIf the defined property has a key that is equal to a key in the given dictionary, the defined property MUST also have keys that match each of the corresponding values.\nNo restriction is inferred from this field for keys in the defined property that do not match any key in the given dictionary.",
                                            "type": "object",
                                            "additionalProperties": {
                                                "type\"": "array",
                                                "items": {
                                                    "type": "string"
                                                },
                                                "uniqueItems": true
                                            }
                                        },
                                        "enum": {
                                            "description": "The defined property MUST take one of the values given in the provided list.",
                                            "type": "array",
                                            "items": {
                                                "$comment": "Must validate against the Property Definition itself, but there is no easy way to express that in the schema."
                                            }
                                        },
                                        "examples": {
                                            "description": "A list of example values that the defined property can have.",
                                            "type": "array",
                                            "items": {
                                                "$comment": "Must validate against the Property Definition itself, but there is no easy way to express that in the schema."
                                            }
                                        },
                                        "items": {
                                            "description": "The defined property is a list where each item MUST match this inner Property Definition.",
                                            "$ref": "#/$defs/propdef"
                                        },
                                        "maxItems": {
                                            "description": "The defined property is an array that MUST contain a number of items that is less than or equal to the given integer.",
                                            "type": "integer",
                                            "minimum": 0
                                        },
                                        "minItems": {
                                            "description": "A non-negative integer. The defined property is an array that MUST contain a number of items that is greater than or equal to the given integer.",
                                            "type": "integer",
                                            "minimum": 0
                                        },
                                        "uniqueItems": {
                                            "description": "If TRUE, the defined property is an array that MUST only contain unique items. If FALSE, this field sets no limitation on the defined property.",
                                            "type": "boolean"
                                        },
                                        "multipleOf": {
                                            "description": "An integer is strictly greater than 0.\nThe defined property MUST have a value that when divided by the given number results in an integer (i.e., it must be even divisible by this value without a fractional part).",
                                            "type": [
                                                "integer",
                                                "number"
                                            ],
                                            "exclusiveMinimum": 0
                                        },
                                        "maximum": {
                                            "description": "The defined property MUST be less than or equal to the given value.",
                                            "type": [
                                                "integer",
                                                "number"
                                            ]
                                        },
                                        "exclusiveMaximum": {
                                            "description": "The defined property MUST be strictly less than the given value; it cannot be equal.",
                                            "type": [
                                                "integer",
                                                "number"
                                            ]
                                        },
                                        "minimum": {
                                            "description": "The defined property MUST be greater than or equal to the given value.",
                                            "type": [
                                                "integer",
                                                "number"
                                            ]
                                        },
                                        "exclusiveMinimum": {
                                            "description": "The defined property MUST be strictly greater than the given value; it cannot be equal.",
                                            "type": [
                                                "integer",
                                                "number"
                                            ]
                                        },
                                        "maxLength": {
                                            "description": "The defined property is a string that MUST have a length that is less than or equal to the given integer.\n(The length of the string is the number of individual Unicode characters it is composed of.)",
                                            "type": "integer",
                                            "minimum": 0
                                        },
                                        "minLength": {
                                            "description": "The defined property is a string that MUST have a length that is less than or equal to the given integer.\n(The length of the string is the number of individual Unicode characters it is composed of.)",
                                            "type": "integer",
                                            "minimum": 0
                                        },
                                        "format": {
                                            "description": "Choose one of the following values to indicate that the defined property is a string that MUST adhere to the specified format:\n- \"date-time\": the date-time production in RFC 3339 section 5.6.\n- \"date\": the full-date production in RFC 3339 section 5.6.\n- \"time\": the full-time production in RFC 3339 section 5.6.\n- \"duration\": the duration production in RFC 3339 Appendix A.\n- \"email\": the \"Mailbox\" ABNF rule in RFC 5321 section 4.1.2.\n- \"uri\": a string instance is valid against this attribute if it is a valid URI according to RFC 3986.\n- \"iri\": a string instance is valid against this attribute if it is a valid IRI according to RFC 3987.",
                                            "type": "string",
                                            "enum": [
                                                "date-time",
                                                "date",
                                                "time",
                                                "duration",
                                                "email",
                                                "uri",
                                                "iri"
                                            ]
                                        },
                                        "$id": {
                                            "description": "A static IRI identifier that is a URN or URL representing the specific version of this level of the defined property.\n(If it is a URL, clients SHOULD NOT assign any interpretation to the response when resolving that URL.)\nIt SHOULD NOT be changed as long as the property definition remains the same, and SHOULD be changed when the property definition changes.\nProperty Definitions SHOULD be regarded as the same if they only differ by:\n- The inclusion or omission of \"null\" in the type in the outermost layer of the definition.\n- Additions of annotating notes to end of the description field.\n- Changes to the following specific fields at any level: deprecated, examples, $comment, x-optimade-implementation, and x-optimade-requirements.",
                                            "type": "string"
                                        },
                                        "title": {
                                            "description": "A short single-line human-readable explanation of the defined property appropriate to show as part of a user interface.",
                                            "type": "string"
                                        },
                                        "description": {
                                            "description": "A human-readable multi-line description that explains the purpose, requirements, and conventions of the defined property.\nThe format SHOULD be a one-line description, followed by a new paragraph (two newlines), followed by a more detailed description of all the requirements and conventions of the defined property.\nFormatting in the text SHOULD use Markdown in the CommonMark v0.3 format format, with mathematical expressions written to render correctly with the LaTeX mode of Mathjax 3.2 <https://docs.mathjax.org/en/v3.2-latest/>.\nWhen possible, it is preferable for mathematical expressions to use as straightforward notation as possible to make them readable also when not rendered.\n\nAdditions appended to the end of the description field that are clearly marked as notes that clarify the definition without changing it are viewed as annotations to the Property Definition rather than an integral part of it.\nSuch annotations SHOULD only be added to the end of an otherwise unmodified description and MUST NOT change the meaning or interpretation of the text above them.\nThe purpose is to provide a way to add explanations and clarifications to a definition without having to regard it as a new definition.\nFor example, these annotations to the description MAY be used to explain why a definition has been deprecated.",
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
                                        },
                                        "x-optimade-unit-definitions": {
                                            "type": "array",
                                            "items": {
                                                "required": [
                                                    "title",
                                                    "symbol",
                                                    "display-symbol",
                                                    "description"
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
                                        "x-optimade-type": {
                                            "type": "string",
                                            "enum": [
                                                "string",
                                                "integer",
                                                "float",
                                                "boolean",
                                                "timestamp",
                                                "list",
                                                "dictionary"
                                            ]
                                        },
                                        "x-optimade-unit": {
                                            "type": "string"
                                        },
                                        "x-optimade-implementation": {
                                            "patternProperties": {
                                                "^x-": {}
                                            },
                                            "properties": {
                                                "query-support": {
                                                    "enum": [
                                                        "all mandatory",
                                                        "equality only",
                                                        "partial",
                                                        "none"
                                                    ],
                                                    "type": "string"
                                                },
                                                "query-support-operators": {
                                                    "items": {
                                                        "enum": [
                                                            "<",
                                                            "<=",
                                                            ">",
                                                            ">=",
                                                            "=",
                                                            "!=",
                                                            "CONTAINS",
                                                            "STARTS WITH",
                                                            "ENDS WITH",
                                                            "HAS",
                                                            "HAS ALL",
                                                            "HAS ANY",
                                                            "HAS ONLY",
                                                            "IS KNOWN",
                                                            "IS UNKNOWN"
                                                        ],
                                                        "type": "string"
                                                    },
                                                    "type": "array"
                                                },
                                                "response-level": {
                                                    "enum": [
                                                        "always",
                                                        "yes",
                                                        "no"
                                                    ]
                                                },
                                                "sortable": {
                                                    "type": "boolean"
                                                },
                                                "$comment": {
                                                    "type": "string"
                                                }
                                            },
                                            "type": "object"
                                        },
                                        "x-optimade-requirements": {
                                            "additionalProperties": false,
                                            "properties": {
                                                "patternProperties": {
                                                    "^x-": {}
                                                },
                                                "query-support": {
                                                    "enum": [
                                                        "all mandatory",
                                                        "equality only",
                                                        "partial",
                                                        "none"
                                                    ],
                                                    "type": "string"
                                                },
                                                "query-support-operators": {
                                                    "items": {
                                                        "enum": [
                                                            "<",
                                                            "<=",
                                                            ">",
                                                            ">=",
                                                            "=",
                                                            "!=",
                                                            "CONTAINS",
                                                            "STARTS WITH",
                                                            "ENDS WITH",
                                                            "HAS",
                                                            "HAS ALL",
                                                            "HAS ANY",
                                                            "HAS ONLY",
                                                            "IS KNOWN",
                                                            "IS UNKNOWN"
                                                        ],
                                                        "type": "string"
                                                    },
                                                    "type": "array"
                                                },
                                                "response-level": {
                                                    "enum": [
                                                        "always",
                                                        "must",
                                                        "should",
                                                        "may",
                                                        "should not",
                                                        "must not"
                                                    ],
                                                    "type": "string"
                                                },
                                                "sortable": {
                                                    "type": "boolean"
                                                },
                                                "support": {
                                                    "enum": [
                                                        "must",
                                                        "should",
                                                        "may"
                                                    ],
                                                    "type": "string"
                                                },
                                                "$comment": {
                                                    "type": "string"
                                                }
                                            },
                                            "type": "object"
                                        },
                                        "$comment": {
                                            "description": "A human-readable comment relevant in the context of the raw definition data.\nThese comments should normally not be shown to the end users.\nComments pertaining to the Property Definition that are relevant to end users should go into the field description.\nFormatting in the text SHOULD use Markdown using the format described in the definition of the description field.\n\nThis fields is an annotation rather than an integral part of the Property Definition.\nProperty Definitions that only differ by fields that are considered annotations are to be considered the same, and as explained in the definition of the $id field SHOULD share the same $id.",
                                            "type": "string"
                                        },
                                        "deprecated": {
                                            "description": "If TRUE, implementations SHOULD not use the defined property, and it MAY be removed in the future.\nIf FALSE, the defined property is not deprecated. The field not being present means FALSE.\n\nThis fields is an annotation rather than an integral part of the Property Definition.\nProperty Definitions that only differ by fields that are considered annotations are to be considered the same, and as explained in the definition of the $id field SHOULD share the same $id.",
                                            "type": "boolean"
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
                "additionalProperties": false
            }
        }
    },
    "additionalProperties": false
}
```