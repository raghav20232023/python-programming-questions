---
title: Questions on Data Processing (Question 2)
tags: ['list_comprehension', 'dictionary', 'filtering']
---

# Problem Statement
Implement the given function according to the docstrings.
Details about the functions to be implemented are given as follows:
def process_data(data):
    """
    Processes a list of product dictionaries to filter, group, and aggregate prices by category.

    Args:
        data (list): A list of dictionaries, where each dictionary contains:
            - 'name' (str): Name of the product.
            - 'category' (str): Category of the product.
            - 'price' (float): Price of the product.

    Returns:
        dict: A dictionary where the keys are categories (str) and the values are 
              the total aggregated price (float) of products in that category 
              priced $50 or less.

    Example:
        >>> data = [
        ...     {'name': 'Product A', 'category': 'Electronics', 'price': 30},
        ...     {'name': 'Product B', 'category': 'Electronics', 'price': 70},
        ...     {'name': 'Product C', 'category': 'Books', 'price': 20},
        ...     {'name': 'Product D', 'category': 'Books', 'price': 40},
        ... ]
        >>> process_data(data)
        {'Electronics': 30, 'Books': 60}
    """

# Solution
```python test.py  -r 'python test.py'
<prefix>

</prefix>
<template>
def process_data(data):
    """
    Processes a list of product dictionaries to filter, group, and aggregate prices by category.

    Args:
        data (list): A list of dictionaries, where each dictionary contains:
            - 'name' (str): Name of the product.
            - 'category' (str): Category of the product.
            - 'price' (float): Price of the product.

    Returns:
        dict: A dictionary where the keys are categories (str) and the values are 
              the total aggregated price (float) of products in that category 
              priced $50 or less.

    Example:
        >>> data = [
        ...     {'name': 'Product A', 'category': 'Electronics', 'price': 30},
        ...     {'name': 'Product B', 'category': 'Electronics', 'price': 70},
        ...     {'name': 'Product C', 'category': 'Books', 'price': 20},
        ...     {'name': 'Product D', 'category': 'Books', 'price': 40},
        ... ]
        >>> process_data(data)
        {'Electronics': 30, 'Books': 60}
    """
    <los>...</los>
    <sol>
    # Filter products priced above $50
    filtered_data = [item for item in data if item['price'] <= 50]

    # Aggregate prices by category
    category_prices = {}
    for item in filtered_data:
        category = item['category']
        if category in category_prices:
            category_prices[category] += item['price']
        else:
            category_prices[category] = item['price']
    
    return category_prices
    </sol>
</template>
<suffix>

</suffix>
<suffix_invisible>
{% include '../function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
is_equal(
    data = [
    {'name': 'Item 1', 'category': 'A', 'price': 10},
    {'name': 'Item 2', 'category': 'A', 'price': 40},
    {'name': 'Item 3', 'category': 'B', 'price': 60},
    {'name': 'Item 4', 'category': 'C', 'price': 50},
],
{'A': 50, 'C': 50}
)

```

## Output 1

```
{'A': 50, 'C': 50}
```


# Private Test Cases

## Input 1

```
is_equal(
    data = [
    {'name': 'X', 'category': 'Food', 'price': 5},
    {'name': 'Y', 'category': 'Food', 'price': 25},
    {'name': 'Z', 'category': 'Stationery', 'price': 50},
],
{'Food': 30, 'Stationery': 50}
)
```

## Output 1

```
{'Food': 30, 'Stationery': 50}
```
