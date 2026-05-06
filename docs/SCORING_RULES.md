# Scoring Rules

## Score Labels
Use these result labels:
- iyi_secim
- orta
- dikkatli_tuket
- sik_tuketme

User-facing Turkish labels:
- İyi Seçim
- Orta
- Dikkatli Tüket
- Sık Tüketme

## Decision Philosophy
The app should not make medical claims.
It should provide practical food label interpretation.

## Ingredient Risk Levels
Each ingredient has:
- low
- medium
- high
- unknown

## Basic Rules

### High Risk Ingredients
If product contains one or more high-risk ingredients:
- Minimum score should be dikkatli_tuket.

If product contains two or more high-risk ingredients:
- Score may be sik_tuketme.

### Processed Meat Category
If category is processed meat:
- Default minimum score is dikkatli_tuket.
- If sodium nitrite or nitrate is present, keep dikkatli_tuket or sik_tuketme depending on other factors.

### Simple Dairy
If category is yogurt and ingredients are only milk and cultures:
- Score may be iyi_secim.

### High Sugar
If ingredients include glucose syrup, fructose syrup, or high sugar indicators:
- Score should be at least dikkatli_tuket.

### Unknown Ingredients
Unknown ingredients should not automatically make a product risky.
Show them as "Bilinmeyen içerik" and ask for moderation later.

## AI Rule
AI must not decide score labels.
AI may only rewrite approved explanations into simpler language.