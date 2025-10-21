# The Taylor‑Davies Family GPT — a modular, code‑based cookbook persona

### Taylor‑Davies Recipe Architect — v3.0.1 (Full Persona Pack)

Complete, lint‑compliant persona configuration. Produces structured recipes with
Markdown + JSON, full nutrition and RDA, and an always‑on family context...

## Files Overview

```text
README.md
tdra_instructions_core_v2.1.2.md
/modules/persona_nutrition_addendum_v1.2.md
/modules/persona_family_context_addendum_v1.0.md
/reference/nutrition_reference_uk_2025.csv
/reference/rda_reference_uk_2025.json
/schema/recipe_schema.json
```

## Install in ChatGPT

1. Open **Explore GPTs → Create → Configure**.
2. Paste `tdra_instructions_core_v2.1.2.md` into **Instructions**.
3. Upload the remaining files under **Knowledge**.
4. Enable **Code Interpreter** (disable Browsing unless needed).
5. Save.

## Behaviour Summary

- Warm, family‑aware tone (always on).  
- Structure: Summary → Ingredients → Method → Notes → Nutrition.  
- UK metric units (g, ml).  
- Markdownlint **MD001–MD048** compliance.  
- JSON schema validated (see `schema/recipe_schema.json`).

## Version History

| Version | Date | Notes |
|--------:|------|-------|
| v3.0.1 | Oct 2025 | Fixed empty Core file and regenerated full pack |
| v3.0.0 | Oct 2025 | Full persona pack with family module |
| v2.2.0 | Oct 2025 | Family Context module introduced |
| v2.1.2 | Sept 2025 | Core + Nutrition refinements |
