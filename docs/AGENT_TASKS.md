# Agent Tasks

## How to Work
Each task must be done separately.
Do not implement future features early.
Do not refactor unrelated files.

## Task Template

### Task
Write the task clearly.

### Goal
What this task should achieve.

### Scope
What should be implemented.

### Out of Scope
What must not be implemented.

### Acceptance Criteria
How we know the task is done.

---

## Task 1 - Create Base Folder Structure

Goal:
Create the project folder structure.

Scope:
- lib/core
- lib/shared
- lib/features/home
- lib/features/search
- lib/features/barcode
- lib/features/product
- lib/features/ocr
- lib/features/analysis
- docs folder

Out of Scope:
- No business logic
- No Supabase
- No barcode
- No OCR

Acceptance:
- Folder structure exists.
- App still runs.

---

## Task 2 - Add Core Dependencies

Goal:
Add required Flutter packages.

Dependencies:
- flutter_riverpod
- go_router
- dio
- logger
- flutter_dotenv
- mobile_scanner
- image_picker
- supabase_flutter

Acceptance:
- flutter pub get works.
- App still runs.

---

## Task 3 - App Theme and Router

Goal:
Create basic theme and routing.

Scope:
- AppTheme
- AppRouter
- HomeScreen route
- SearchScreen route placeholder
- BarcodeScreen route placeholder
- ProductDetail route placeholder

Acceptance:
- App opens HomeScreen.
- Navigation to placeholder screens works.

---

## Task 4 - Supabase Setup

Goal:
Initialize Supabase in Flutter.

Scope:
- Add .env.example
- Add Supabase initialization
- Add Supabase service wrapper
- Read URL and anon key from env

Out of Scope:
- No database queries yet

Acceptance:
- App starts with Supabase initialized.
- Missing env shows clear error.

---

## Task 5 - Database Migrations

Goal:
Create Supabase migration files.

Scope:
- products
- categories
- ingredients
- product_reviews
- product_ingredients
- user_submissions
- scan_logs

Acceptance:
- Migrations apply successfully.
- Tables exist in Supabase.

---

## Task 6 - Seed Data

Goal:
Add test product and ingredient data.

Scope:
- 5 categories
- 10 ingredients
- 5 products
- 5 product reviews

Acceptance:
- Data visible in Supabase.
- App can later query this data.

---

## Task 7 - Product Search

Goal:
Build product search feature.

Scope:
- Product model
- ProductRepository
- SearchController
- SearchScreen
- Product cards
- Empty/loading/error states

Acceptance:
- User can search products.
- Results are shown.
- Product card click navigates to detail.

---

## Task 8 - Product Detail

Goal:
Show product analysis detail.

Scope:
- ProductDetailScreen
- Fetch product by id
- Show product review
- Show ingredients
- Show verification status

Acceptance:
- Product detail opens and displays readable analysis.

---

## Task 9 - Barcode Scanner

Goal:
Scan barcode and find product.

Scope:
- mobile_scanner integration
- BarcodeScreen
- Search product by barcode
- Navigate to product detail if found
- Show not found screen if missing

Acceptance:
- Barcode scanner reads barcode.
- Found product opens detail.
- Missing product shows fallback.

---

## Task 10 - OCR Placeholder

Goal:
Create initial OCR flow UI.

Scope:
- Ingredients photo screen
- Image picker
- OCR result editable text area placeholder

Out of Scope:
- Actual OCR processing can be added next

Acceptance:
- User can select/take photo.
- User can continue to editable text screen.

---

## Task 11 - Ingredient Matcher

Goal:
Match typed/OCR ingredient text to ingredients database.

Scope:
- Normalize text
- Split ingredients
- Match by name, alternative_names, e_code
- Return matched and unmatched ingredients

Acceptance:
- "sodyum nitrit, sodyum polifosfat" matches known ingredients.

---

## Task 12 - Analysis Engine

Goal:
Generate simple rule-based analysis.

Scope:
- Apply scoring rules from SCORING_RULES.md
- Generate score_label
- Generate warning list
- Generate summary

Acceptance:
- Matched high-risk ingredients produce dikkatli_tuket or sik_tuketme.