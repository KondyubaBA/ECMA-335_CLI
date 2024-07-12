## Field

- Flags (a 2-byte bitmask of type FieldAttributes, §II.23.1.5)
- Name (an index into the String heap)
- Signature (an index into the Blob heap)

II.23.1.5 Flags for fields [FieldAttributes]
|Flag              |Value |Description                                      |
|------------------|------|-------------------------------------------------|
|FieldAccessMask   |0x0007|These 3 bits contain one of the following values:|
|                  |      |                                                 |
|CompilerControlled|0x0000|                                                 |
|Private           |0x0001|                                                 |
|FamANDAssem       |0x0002|                                                 |
|Assembly          |0x0003|                                                 |
|Family            |0x0004|                                                 |
|FamORAssem        |0x0005|                                                 |
|Public            |0x0006|                                                 |
|                  |      |                                                 |
|Static            |0x0010|                                                 |
|InitOnly          |0x0020|                                                 |
|Literal           |0x0040|                                                 |
|NotSerialized     |0x0080|                                                 |
|SpecialName       |0x0200|                                                 |
|                  |      |Interop Attributes                               |
|PInvokeImpl       |0x2000|                                                 |
|                  |      |Additional flags                                 |
|RTSpecialName     |0x0400|                                                 |
|HasFieldMarshal   |0x1000|                                                 |
|HasDefault        |0x8000|                                                 |
|HasFieldRVA       |0x0100|                                                 |

