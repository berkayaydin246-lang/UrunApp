# Database Schema

## products

Fields:
- id uuid primary key
- barcode text unique nullable
- name text not null
- normalized_name text
- brand text
- category_id uuid nullable
- image_url text nullable
- ingredients_text text nullable
- nutrition_text text nullable
- source text nullable
- source_url text nullable
- verification_status text default 'pending'
- created_at timestamp
- updated_at timestamp

Verification statuses:
- verified
- pending
- imported
- user_submitted
- rejected

## categories

Fields:
- id uuid primary key
- name text not null
- parent_id uuid nullable
- default_processing_level text nullable
- default_warning text nullable

## ingredients

Fields:
- id uuid primary key
- name text not null
- normalized_name text not null
- alternative_names text[] nullable
- e_code text nullable
- category text nullable
- risk_level text not null
- short_description text
- long_description text
- source_url text nullable
- created_at timestamp
- updated_at timestamp

Risk levels:
- low
- medium
- high
- unknown

## product_ingredients

Fields:
- id uuid primary key
- product_id uuid references products(id)
- ingredient_id uuid references ingredients(id)
- raw_text text
- detected_from text
- confidence_score numeric nullable

## product_reviews

Fields:
- id uuid primary key
- product_id uuid references products(id)
- score_label text not null
- summary text
- warning_text text
- positive_points text[] nullable
- negative_points text[] nullable
- consumption_advice text
- suitable_for_children boolean nullable
- review_status text default 'draft'
- reviewed_by uuid nullable
- updated_at timestamp

Score labels:
- iyi_secim
- orta
- dikkatli_tuket
- sik_tuketme

## user_submissions

Fields:
- id uuid primary key
- user_id uuid nullable
- barcode text nullable
- product_name text nullable
- front_image_url text nullable
- ingredients_image_url text nullable
- nutrition_image_url text nullable
- ocr_text text nullable
- status text default 'pending'
- admin_note text nullable
- created_at timestamp

Statuses:
- pending
- approved
- rejected
- needs_more_info

## scan_logs

Fields:
- id uuid primary key
- user_id uuid nullable
- input_type text not null
- query_text text nullable
- barcode text nullable
- product_id uuid nullable
- result_status text not null
- created_at timestamp

Input types:
- search
- barcode
- ocr