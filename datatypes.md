# Datatypes

| Name | Size (bytes) |
| --- | --- |
| Boolean | 1 |
| Byte | 1 |
| UByte | 1 |
| Short | 2 |
| UShort | 2 |
| Int | 4 |
| Long | 8 |
| Float | 4 |
| Double | 8 |
| String (n) | ≥ 1 ≤ (n * 4) + 3 |
| Chat | ≥ 1, ≤ (32767 * 4) + 3 |
| Identifier | ≥ 1, ≤ (32767×4) + 3 |
| VarInt | ≥ 1, ≤ 5 |
| VarLong | ≥ 1, ≤ 10 |
| Entity Metadata | Varies |
| Slot | Varies |
| NBT | Varies |
| Position | 8 |
| Angle | 1 |
| UUID | 16 |
| Array | Varies |
| Switch | Varies |
| Option | ≥ 1, Varies |
| Compound | Varies |

| Optional X | 0 or size of X |
| Array of X | count * size of X |
| X Enum | size of X |
| Byte Array | Varies |

## Basic Datatype

### Required Keys

| Name |
| --- |
| `type` |

### Optional Keys

| Name | Default Value |
| --- | --- |
| `name` | `None` |
| `options` | `{}` |

```json
{
    "name": "<object_name>",
    "type": "<type_name>",
    "options": {
        ...
    }
}
```

## Strings

Some strings have a max length associated with them. If a string has a max length the key `options.max_length` will be set with the maximum number of characters in the string

Example:
```json
{
    "name": "Server Address",
    "type": "String",
    "options": {
        "max_length": 255
    }
}
```

## Enum

Some numbers represent enums. Enums will have the key `options.enum` set with the name of the corresponding enum.

Example:
```json
{
    "name": "Next State",
    "type": "VarInt",
    "options": {
        "enum": "Handshaking Next State"
    }
}
```

# Complex Datatypes

## Array

### Required Keys

| Key |
| --- |
| `type` |
| `options.count.type` |
| `options.element.type` |

### Optional Keys

| Key | Default Value |
| --- | --- |
| `name` | `None` |

```json
{
    "name": "<object_name>",
    "type": "Array",
    "options": {
        "count": {
            "type": "<count_type>"
        },
        "element": {
            "type": "<arr_element_type>"
        }
    }
}
```

## Switch

### Required Keys

| Key |
| --- |
| `type` |
| `options.switch.type` |
| `options.cases` |

### Optional Keys

| Key | Default Value |
| --- | --- |
| `name` | `None` |

```json
{
    "name": "<object_name>",
    "type": "Switch",
    "options": {
        "switch": {
            "type": "<switch_type>"
        },
        "cases": [
            {
                "value": "<case1_value>",
                "fields": [
                    {
                        "name": "<field1_name>",
                        "type": "<field1_type>",
                        "options": {
                            ...
                        }
                    },
                    {
                        "name": "<field2_name>",
                        "type": "<field2_type>",
                        "options": {
                            ...
                        }
                    }
                ]
            },
            {
                "value": "<case2_value>",
                "fields": [
                    {
                        "name": "<field1_name>",
                        "type": "<field1_type>",
                        "options": {
                            ...
                        }
                    }
                ]
            }
        ]
    }
}
```

## Option

### Required Keys

| Key |
| --- |
| `type` |
| `options.optional.type` |

### Optional Keys

| Key | Default Value |
| --- | --- |
| `name` | `None` |

```json
{
    "name": "<object_name>",
    "type": "Option",
    "options": {
        "optional": {
            "type": "<optional_type>"
        }
    }
}
```

## Compound

### Required Keys

| Key |
| --- |
| `type` |
| `options.fields` |

### Optional Keys

| Key | Default Value |
| --- | --- |
| `name` | `None` |

```json
{
    "name": "<object_name>",
    "type": "Compound",
    "options": {
        "fields": [
            {
                "name": "<field1_name>",
                "type": "<field1_type>",
                "options": {
                    ...
                }
            },
            {
                "name": "<field2_name>",
                "type": "<field2_type>",
                "options": {
                    ...
                }
            }
        ]
    }
}
```
