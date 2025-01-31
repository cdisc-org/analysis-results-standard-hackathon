# Slot: sectionType


_The type of display section that contains one or more pieces of informational text._



URI: [ars:sectionType](https://www.cdisc.org/ars/1-0/sectionType)



<!-- no inheritance hierarchy -->




## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
[DisplaySection](DisplaySection.md) | A part of a tabular display containing one or more pieces of informational te... |  no  |
[GlobalDisplaySection](GlobalDisplaySection.md) | A global definition for part of a tabular display containing one or more piec... |  no  |







## Properties

* Range: [DisplaySectionTypeEnum](DisplaySectionTypeEnum.md)






## Examples

| Value |
| --- |
| Title |
| Footnote |
| Legend |
| Abbreviation |

## Identifier and Mapping Information







### Schema Source


* from schema: https://www.cdisc.org/ars/1-0




## LinkML Source

<details>
```yaml
name: sectionType
description: The type of display section that contains one or more pieces of informational
  text.
examples:
- value: Title
- value: Footnote
- value: Legend
- value: Abbreviation
from_schema: https://www.cdisc.org/ars/1-0
rank: 1000
alias: sectionType
domain_of:
- DisplaySection
- GlobalDisplaySection
range: DisplaySectionTypeEnum

```
</details>