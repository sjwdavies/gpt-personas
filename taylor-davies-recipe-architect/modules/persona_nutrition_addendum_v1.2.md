# Addendum Module: Nutrition and RDA Calculation v1.2

## Purpose

Extends the Core with nutrition, macro, and RDA calculations.

## Calculation Rules (strict)

Required nutrients (compute all):

- energy_kcal
- protein_g
- carbs_g
- fat_g
- salt_g

Data sources:

- per‑100 g baselines: `nutrition_reference_uk_2025.csv`
- RDA tables (adult and child bands): `rda_reference_uk_2025.json`

Mapping:

- Case‑insensitive, fuzzy contains match from ingredient name to a canonical
  baseline.
- If multiple matches exist, choose the most specific and record the choice in
  `meta.assumptions[]`.

Unit to gram:

- tsp = 5 g
- tbsp = 15 g
- ml = 1 g
- L = 1000 g
- g = g
- kg = 1000 g

If unitless whole items, assume 100 g unless clearly specified and record the
assumption.

Math:

1. Convert each ingredient to grams.
2. Sum per‑100 g macros proportionally for the whole recipe.
3. Divide by adult portions to obtain per‑adult‑portion values.
4. Adult %RDA = per‑portion value divided by adult RDA.
5. Child %RDA = per‑portion value divided by the selected child‑band RDA.
6. Also compute a full table for all child bands.

Rounding:

- kcal: 0 dp
- protein, carbs, fat: 1 dp
- salt: 2 dp
- %RDA: 1 dp

JSON output (required):

- `nutrition`: object with energy_kcal, protein_g, carbs_g, fat_g, salt_g
- `meta.adult_rda_percent`: same keys
- `meta.child_rda_percent`: same keys for the selected child band
- `meta.child_rda_percent_by_band`: object of bands mapping to the same keys
- `meta.child_age_band`: string label of the selected band
- `meta.assumptions[]`: short strings describing mappings, conversions, and
  omissions

Markdown output:

- Include both tables described in the Core Nutrition block.
- Use an em dash (—) for any missing numeric in the Markdown tables.
- Follow markdownlint MD001–MD048, including line length and blank line rules.
