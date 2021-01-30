# Datatypes

| Name | Size (bytes) |
| --- | --- |
| Boolean | 1 |
| Byte | 1 |
| Unsigned Byte | 1 |
| Short | 2 |
| Unsigned Short | 2 |
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
| Optional X | 0 or size of X |
| Array of X | count * size of X |
| X Enum | size of X |
| Byte Array | Varies |



# Data Structures

## Array

```json
{
    "type": "Array",
    "options": {
        "type": "type",
        "count_type": "type"
    }
}
```

## Switch

```json
{
    "type": "Switch",
    "switch_type": "type",
    "case": {
        "value1": [
            {
                "name": "field1_name",
                "type": {
                    "type": "field1_type"
                }
            },
            {
                "name": "field2_name",
                "type": {
                    "type": "field2_type"
                }
            }
        ],
        "value2": [
            {
                "name": "field1_name",
                "type": {
                    "type": "field1_type"
                }
            }
        ]
    }
}
```
