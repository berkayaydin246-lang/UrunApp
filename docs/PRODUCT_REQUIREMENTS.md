# Product Requirements

## MVP Features

### Product Search
Users can search products by name or brand.

Requirements:
- Search input
- Product list
- Empty state
- Loading state
- Error state
- Product detail navigation

### Product Detail
Users can view product analysis.

Show:
- Product name
- Brand
- Product image
- Score label
- Short summary
- Ingredients
- Warnings
- Consumption advice
- Verification status

### Barcode Scan
Users can scan a barcode.

Flow:
1. Scan barcode.
2. Search local database.
3. If found, open product detail.
4. If not found, try external source.
5. If still not found, show product not found screen.

### Ingredients Photo OCR
If product is missing, user can upload/take a photo of the ingredients list.

Flow:
1. User takes ingredients photo.
2. OCR extracts text.
3. User can correct OCR text.
4. System matches ingredients.
5. System generates rule-based analysis.

### Analysis Result
Show a simple result:
- İyi Seçim
- Orta
- Dikkatli Tüket
- Sık Tüketme

### User Submission
If a product is missing, user can submit:
- Product name
- Barcode
- Front image
- Ingredients image
- OCR text

Admin will review later.

## Out of Scope for MVP
- AI chatbot
- Personalized diet plans
- Price comparison
- Social media/community features
- Front package image recognition
- Advanced recommendation engine
- Medical advice