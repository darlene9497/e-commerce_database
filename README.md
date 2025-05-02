# E-commerce_database

## 📌 Getting Started

1. Clone or download this repository.
2. Open your MySQL client (Workbench, CLI etc.).
3. Run the `ecommerce.sql` file to create the database structure.

## 🗃️ Tables overview

| Table Name          | Description |
|---------------------|-------------|
| `brand`             | Stores brand names and descriptions. |
| `product_category`  | Groups products into categories like clothing, electronics. |
| `product`           | Contains general product information. |
| `product_image`     | Stores image URLs and alt text for each product. |
| `color`             | Defines available colors and their hex codes. |
| `size_category`     | Groups size types like clothing sizes, shoe sizes. |
| `size_option`       | Contains specific sizes (e.g., S, M, L, 42). |
| `product_variation` | Represents unique product combinations (e.g., red shoe size 42). |
| `product_item`      | Stores stock and SKU for variations. |
| `attribute_category`| Groups attributes (e.g., physical, technical). |
| `attribute_type`    | Defines attribute types: text, number, boolean. |
| `product_attribute` | Stores product-specific details like material, specs. |

## 🔑 Keys & constraints

- **Primary keys** uniquely identify records in each table.
- **Foreign keys** enforce relationships between:
  - `product` → `brand`, `product_category`
  - `product_image` → `product`
  - `product_variation` → `product`, `color`, `size_option`
  - `size_option` → `size_category`
  - `product_item` → `product_variation`
  - `product_attribute` → `product`, `attribute_category`, `attribute_type`

![IMG](/ecommerce.png)
[E-commerce database ERD](https://dbdiagram.io/d/E-commerce-Database-6814a6391ca52373f53449dc)

## 💡 Example use case

With this schema, you can:

- Display a product with multiple sizes and colors.
- Manage stock levels for each variant.
- Show detailed product attributes (e.g., material, weight, processor).
- Filter products by categories, attributes, or brands.

## 📦 Requirements

- MySQL 5.7+ or compatible RDBMS
- SQL client or IDE for execution
