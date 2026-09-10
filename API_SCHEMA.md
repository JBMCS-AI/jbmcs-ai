# JBMCS AI Core - API Schema Specification (v1.0)

## Overview
This document defines the relational database schema and API structure for the JBMCS AI Core PostgreSQL backend hosted on Supabase.

---

## 1. Core Knowledge Base Schemas

### `product_categories`
* **id** (`uuid`, Primary Key): Auto-generated unique identifier.
* **category_type** (`text`): Broad footwear group (`Shoes`, `Slippers`, `Sandals`).
* **subtype** (`text`): Specific design category (`Oxford`, `Derby`, `Loafer`, etc.).
* **created_at** (`timestamptz`): Record timestamp.

### `footwear_components`
* **id** (`uuid`, Primary Key): Auto-generated unique identifier.
* **component_name** (`text`, Unique): Component element name (`Upper`, `Lining`, `Outsole`, etc.).
* **created_at** (`timestamptz`): Record timestamp.

### `construction_methods`
* **id** (`uuid`, Primary Key): Auto-generated unique identifier.
* **method_name** (`text`, Unique): Assembly technique (`Blake Stitch`, `Goodyear Welt`, etc.).
* **created_at** (`timestamptz`): Record timestamp.

---

## 2. Cost & Manufacturing Schemas

### `materials`
* **material_id** (`text`, Primary Key): Unique traceability ID (e.g., `MAT-LEA-001`).
* **material_name** (`text`): Material commercial name.
* **material_category** (`text`): Primary classification (`Leather`, `Textile`, etc.).
* **yield_waste_percent** (`decimal`): Expected manufacturing waste yield percentage.
* **hide_size_sqft** (`decimal`): Standard material unit size in square feet.
* **unit_cost** (`decimal`): Cost per square foot/unit.
* **created_at** (`timestamptz`): Record timestamp.

### `manufacturing_processes`
* **process_id** (`text`, Primary Key): Process code (e.g., `MFG-001`).
* **process_name** (`text`): Operation name (`Pattern Cutting`, `Edge Skiving`).
* **description** (`text`): Step operational summary.
* **created_at** (`timestamptz`): Record timestamp.

---

## 3. Governance & Audit Schema

### `decision_log`
* **decision_id** (`text`, Primary Key): Project governance record ID (e.g., `D-008`).
* **description** (`text`): Strategic or architectural decision description.
* **status** (`text`): Policy status (`Approved`, `Pending`).
* **created_at** (`timestamptz`): Record timestamp.

