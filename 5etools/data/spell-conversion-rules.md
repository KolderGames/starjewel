SPELL-TO-MARKDOWN CONVERSION RULES

Scope and order
- Convert every entry in the JSON "spell" or "spells" list.
- Sort spells alphabetically, removing leading backticks and spaces.
- Preserve unfinished spells and placeholders.
- Do not invent missing rules or silently change spell mechanics.
- Explicit corrections I provide override the JSON.

Layout
Use this structure for each spell:

---
#### Spell Name
_Level N School (Class, Class)_

**Casting Time:**  :: value
**Range:**         :: value
**Components:**    :: value
**Duration:**      :: value

Spell description.

For level 0 spells, use:
_School Cantrip (Class, Class)_

Terminology
- Expand school codes using the mapping below:
  A = Abjuration
  C = Conjuration
  D = Divination
  E = Enchantment
  G = Negation
  I = Illusion
  N = Necromancy
  R = Primal
  T = Transmutation
  V = Evocation
- Flag unknown school codes instead of guessing.
- Omit the class parentheses when no classes are listed.

Spell details
- Preserve reaction triggers in Casting Time.
- Indicate ritual casting with "(ritual)".
- Write concentration durations as
  "Concentration, up to [duration]".
- Include material descriptions, costs, and consumption.
- Preserve range shapes and dimensions.
- Render any references to primal forces (ahn, dan, fel, lin, mas, nok, pen, and tek) as:
  _primal force_

Descriptions
- Preserve wording, capitalization, and paragraph breaks.
- Replace JSON reference tags with their readable display text.
- Remove source identifiers and internal metadata.
- Preserve dice expressions and damage values.
- Render named subsections as:
  **_Subsection Name._** Text
- Preserve lists as paragraphs.

Tables
- Convert every table into a Markdown table.
- Put its caption above it as a level-five heading:
  ##### Table Name
- Use left-aligned columns.
- Preserve row order and cell contents.
- Do not add tables unless explicitly instructed.

Higher-level casting
- Place higher-level casting information after the description.
- Use:
  **_Using a Higher-Level Spell Slot._** Text
- Format Cantrip Upgrade in the same way.

Validation and delivery
- Verify that every spell appears exactly once.
- Verify alphabetical order and removal of JSON reference tags.
- Save the complete result as a .md file.
- Report ambiguities separately from the spell text.