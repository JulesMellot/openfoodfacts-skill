---
name: open-food-facts
description: Look up food product information from the OpenFoodFacts database using a barcode or a product name search.
---

# Instructions

Use the `run_js` tool with the following parameters:

- data: A JSON string with ONE of the following fields:
  - barcode: String - the EAN/UPC barcode of the product (e.g. "3017620422003")
  - query: String - a product name or keyword to search for (e.g. "Nutella")

## Examples

Look up Nutella by barcode:
```json
{ "barcode": "3017620422003" }
```

Search by name:
```json
{ "query": "Nutella" }
```

## Output

The tool returns a JSON object with:
- `product`: main product info (name, brand, quantity)
- `nutriscore`: Nutri-Score grade (a–e)
- `nova`: NOVA group (1–4, food processing level)
- `ecoscore`: Eco-Score grade
- `ingredients`: ingredients text
- `nutrition`: key nutrition facts per 100g (energy_kcal, fat, saturated_fat, carbohydrates, sugars, fiber, proteins, salt)
- `labels`: quality labels (organic, fair trade, etc.)
- `image_url`: front image URL of the product

When presenting results, always highlight the Nutri-Score, NOVA group, and key nutrition facts. Warn the user if the product has a high sugar, salt or saturated fat content.
