---
title: Questions on Data Processing (Question 2) IO
tags: ['dictionary', 'io', 'map', 'lambda', 'filter']
---

# Problem Statement
Implement the given function according to the docstrings.
Details about the functions to be implemented are given as follows:
"""
    Reads monthly revenues from standard input, processes them using map, filter, and reduce, 
    and prints the total revenue of qualifying months.

    Input:
        A single line of space-separated integers representing monthly revenues.

    Output:
        A single integer, which is the total revenue from months where post-tax revenue > 1000.

    Example:
        Input:
            1200 900 1500 2000
        Output:
            3150
        Explanation:
            After 10% tax deduction: [1080, 810, 1350, 1800]
            Months with post-tax revenue > 1000: [1080, 1350, 1800]
            Total revenue: 1080 + 1350 + 1800 = 4230
    """

# Solution
```py3 test.py  -r 'python test.py'
<prefix>

</prefix>
<template>
def calculate_revenue():
    """
    Reads monthly revenues from standard input, processes them using map, filter, and reduce, 
    and prints the total revenue of qualifying months.

    Input:
        A single line of space-separated integers representing monthly revenues.

    Output:
        A single integer, which is the total revenue from months where post-tax revenue > 1000.

    Example:
        Input:
            1200 900 1500 2000
        Output:
            3150
        Explanation:
            After 10% tax deduction: [1080, 810, 1350, 1800]
            Months with post-tax revenue > 1000: [1080, 1350, 1800]
            Total revenue: 1080 + 1350 + 1800 = 4230
    """
    <los>...</los>
    <sol>
    # Read input from stdin
    data = input().strip().split()
    revenues = list(map(int, data))

    # Map: Apply 10% tax deduction to each revenue
    post_tax = map(lambda x: x * 0.9, revenues)

    # Filter: Keep only months with post-tax revenue > 1000
    qualifying_months = filter(lambda x: x > 1000, post_tax)

    # Reduce: Calculate the total revenue of qualifying months
    total_revenue = 0
    for revenue in qualifying_months:
        total_revenue += revenue

    # Print the result
    print(int(total_revenue))

calculate_revenue()</sol>

</template>
<suffix>

</suffix>
<suffix_invisible>
{% include './function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
1000 1500 2000 500
```

## Output 1

```
3150
```


# Private Test Cases

## Input 1

```
1200 900 1500 2000
```

## Output 1

```
4230
```
