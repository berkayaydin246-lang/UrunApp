# CLAUDE.md

## Project Name
Food Analyzer App

## Project Summary
This is a Flutter + Supabase mobile app for food product analysis in Turkey.

Users can:
- Search products by name
- Scan product barcodes
- Upload an ingredients photo when product data is missing
- See simple Turkish explanations of food ingredients
- Understand whether a product should be consumed carefully

## Core Product Flow
1. User searches product by name.
2. If product exists, show stored product analysis.
3. If product does not exist, suggest barcode scanning.
4. If barcode exists, fetch product from local database.
5. If barcode is missing locally, try external data sources such as Open Food Facts.
6. If still not found, ask user to upload ingredients photo.
7. OCR extracts text.
8. Ingredients are matched against the ingredients database.
9. Rule-based analysis generates a simple result.
10. AI may only be used to simplify explanation text, not to make health decisions.

## Tech Stack
- Flutter
- Dart
- Supabase
- PostgreSQL
- Supabase Edge Functions
- Riverpod
- GoRouter
- Dio
- mobile_scanner
- image_picker
- Google ML Kit OCR later

## Important Rules
- Do not add unnecessary features.
- Do not implement AI as the main decision engine.
- Health decisions must be based on database rules, not AI guesses.
- Keep UI simple, readable, and suitable for 50+ users.
- Every screen must have loading, error, and empty states.
- Use feature-based folder structure.
- Keep code modular and maintainable.
- Do not expose Supabase service_role key in Flutter client.
- Any admin-only operation must happen on backend/Edge Functions.
- Do not invent medical claims.
- Use clear Turkish UI text.

## Folder Structure
Use this structure:

lib/
  core/
    constants/
    theme/
    router/
    services/
    utils/
  shared/
    widgets/
    extensions/
  features/
    home/
    search/
    barcode/
    product/
    ocr/
    analysis/
    history/

supabase/
  migrations/
  functions/

docs/

## Development Style
Before coding:
1. Read CLAUDE.md.
2. Read docs/PROJECT_OVERVIEW.md.
3. Read docs/DEVELOPMENT_PLAN.md.
4. Complete only the assigned task.
5. Do not refactor unrelated files.
6. After changes, explain what changed and which files were touched.

## MVP Priority
Build in this order:
1. Project structure
2. Theme and routing
3. Supabase setup
4. Database schema
5. Product search
6. Product detail
7. Barcode scanning
8. Open Food Facts import
9. OCR ingredients photo
10. Ingredient matching
11. Rule-based analysis
12. Admin/moderation system