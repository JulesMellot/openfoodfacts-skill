---
name: open-food-facts
description: Look up food product info by barcode or name using OpenFoodFacts.
---

# Instructions

Use the `run_js` tool with the following parameters:

- data: A JSON string with ONE of the following fields:
  - barcode: String - the EAN/UPC barcode (e.g. "3017620422003")
  - query: String - a product name to search (e.g. "Nutella")

## Examples

By barcode:
```json
{ "barcode": "3017620422003" }
```

By name:
```json
{ "query": "Nutella" }
```

## Output

Returns: product name, brand, Nutri-Score (a-e), NOVA group (1-4), Eco-Score, ingredients, nutrition per 100g (energy_kcal, fat, saturated_fat, carbohydrates, sugars, fiber, proteins, salt), labels, image_url.

Always highlight the Nutri-Score and NOVA group. Warn if sugar, salt or saturated fat is high.