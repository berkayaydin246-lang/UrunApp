# Development Plan

## Phase 1 - Project Foundation
Goal: Create the base Flutter project structure.

Tasks:
1. Create folder structure.
2. Add dependencies.
3. Set up app theme.
4. Set up routing.
5. Create home screen.
6. Create shared UI components.

Acceptance:
- App opens successfully.
- Home screen displays search and scan actions.
- Routing works.

## Phase 2 - Supabase Setup
Goal: Connect app to Supabase.

Tasks:
1. Add Supabase dependency.
2. Configure environment variables.
3. Initialize Supabase client.
4. Create database migrations.
5. Add seed test data.

Acceptance:
- App can connect to Supabase.
- Product data can be fetched.

## Phase 3 - Product Search
Goal: Users can search products.

Tasks:
1. Create Product model.
2. Create ProductRepository.
3. Create search screen.
4. Add search state management.
5. Show product list.
6. Navigate to detail.

Acceptance:
- Searching "sucuk" returns matching products.
- Empty state appears when nothing is found.

## Phase 4 - Product Detail
Goal: Show stored product analysis.

Tasks:
1. Create product detail screen.
2. Show product name, brand, image.
3. Show score label.
4. Show summary and warnings.
5. Show ingredients.

Acceptance:
- Product detail opens from search.
- Analysis is readable and simple.

## Phase 5 - Barcode
Goal: Scan barcode and find product.

Tasks:
1. Add barcode scanner screen.
2. Read barcode using mobile_scanner.
3. Query local database.
4. If found, open product detail.
5. If not found, show product not found screen.

Acceptance:
- Barcode scan works on Android.
- Found products open correctly.

## Phase 6 - External Product Import
Goal: Try Open Food Facts when barcode is missing locally.

Tasks:
1. Create Edge Function for barcode lookup.
2. Query local DB first.
3. Query Open Food Facts if missing.
4. Normalize result.
5. Insert imported product as verification_status = imported.

Acceptance:
- External product data can be imported.
- Imported products can be viewed in app.

## Phase 7 - OCR
Goal: Analyze ingredients photo when product is missing.

Tasks:
1. Add image picker/camera.
2. Extract text using OCR.
3. Show editable OCR result.
4. Send OCR text to ingredient matcher.

Acceptance:
- User can take/upload ingredients photo.
- OCR text is displayed and editable.

## Phase 8 - Analysis Engine
Goal: Produce rule-based analysis from ingredients.

Tasks:
1. Match OCR text to ingredients table.
2. Apply risk scoring rules.
3. Generate score label.
4. Generate warnings.
5. Show analysis result.

Acceptance:
- Known ingredients are detected.
- Result label is generated.

## Phase 9 - User Submissions
Goal: Grow product database from users.

Tasks:
1. Create submission form.
2. Upload photos to storage.
3. Save submission.
4. Add admin review workflow later.

Acceptance:
- Missing product can be submitted.
- Submission appears in database.

## Phase 10 - Admin Panel
Goal: Moderate product data.

Tasks:
1. Create admin app or Supabase Studio workflow.
2. Review user submissions.
3. Approve products.
4. Edit ingredients.
5. Edit reviews.

Acceptance:
- Pending submissions can be approved.