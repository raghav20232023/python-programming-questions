---
title: Operations on common data types in python
tags: ['int', 'list', 'float', 'string', 'tuple', 'set', 'dict']
---

# Problem Statement
Implement all the given functions according to the docstrings. 
Details about the functions to be implemented are given as follows:

def find_minimum_element(input_set: set) -> int | float | None:
    """
    Finds the minimum element in a set without using explicit loops.

    Args:
        input_set: The input set.

    Returns:
        The minimum element in the set, or None if the set is empty.
        Raises TypeError if the set contains elements of mixed comparable types.

    Raises:
        TypeError: If the set contains elements of mixed comparable types
                   (e.g., integers and strings).

    Examples:
        >>> find_minimum_element({1, 2, 3, 4, 5})
        1
        >>> find_minimum_element(set())
        None
    """

def combined_list_operations(lst: list) -> list:
    """
    Performs a combination of list operations:
    1. Extracts the first and last three elements (or all available if fewer than 3).
    2. Reverses the extracted first elements.
    3. Takes every other element from the reversed first elements.
    4. Takes every other element from the last elements.
    5. Concatenates the results.

    Args:
        lst: The input list.

    Returns:
        A new list with the combined operations applied.

    Example:
    Input: 
    combined_list_operations([1, 2, 3, 4, 5, 6, 7, 8, 9])
    Output:
    [3, 1, 7, 9]
    """

def quadratic_solution_positive(a: float, b: float, c: float) -> float:
    '''
    Given three coefficients of a quadratic equation, return the positive solution.

    Arguments:
    a: float - the coefficient of x^2
    b: float - the coefficient of x
    c: float - the constant term

    Return:
    float - the positive solution

    Example:
    Input : a = 1, b = -5, c = 6
    Output : 3.0
    '''

def arithmetic_operations(t: tuple) -> tuple:
    '''
    Given a tuple of two integers (a, b), return a tuple containing the 
    product, floor division, exponentiation, and remainder of the two numbers.

    Arguments:
    t: tuple - a tuple of two integers (a, b)

    Return:
    tuple - product, floor division, exponentiation, and remainder of the two numbers.

    Example:
    >>> arithmetic_operations((1, 2))
    (2, 0, 1, 1)
    '''

def reverse_interleave(s: str) -> str:
    '''
    Given a string, return a string with the characters interleaved in reverse order.

    Arguments:
    s: str - the input string

    Return:
    str - the string with the characters interleaved in reverse order.

    Example:
    Input : s = "abcdef"
    Output : "fdbeca"
    '''

def flip_transform_dict(d: dict) -> dict:
    '''
    Given a dictionary, return a dictionary with the keys and values flipped.

    Arguments:
    d: dict - the input dictionary

    Return:
    dict - the dictionary with the keys and values flipped.

    Example:
    Input : d = {"a": 1, "b": 2}
    Output : {1: "a", 2: "b"}    
    '''

def simple_list_operations(lst: list) -> list:
    """
    Performs a sequence of simple list operations using slicing, concatenation, and if/else:

    1. Extracts the first two and last two elements (or all available if fewer).
    2. "Appends" the string "END" to the extracted first elements.
    3. "Inserts" the string "START" at the beginning of the extracted first elements.
    4. "Extends" the extracted last elements with the list ['A', 'B'].
    5. Concatenates all results.
    6. Returns the resulting list.

    Args:
        lst: The input list.

    Returns:
        A new list with the operations applied.

    Example:
    Input:
    >>> simple_list_operations([1, 2, 3, 4, 5])
    Output:
    ['START', 1, 2, 'END', 4, 5, 'A', 'B']
    """

def swap_digits(n: int) -> int | str:
    """
    Swaps the digits of a two-digit integer, including negative numbers.

    Args:
        n: The two-digit integer.

    Returns:
        The integer with digits swapped.
        Returns an error message string if the input is not a two-digit number.

    Example:
    Input:
    >>> swap_digits(12)
    Output:
    21
    
    >>> swap_digits(90)
    9
    >>> swap_digits(-12)
    -21
    >>> swap_digits(100)
    Input must be a two-digit number
    """

# Solution
```py3 test.py  -r 'python test.py'
<prefix>

</prefix>
<template>
def find_minimum_element(input_set: set) -> int | float | None:
    """
    Finds the minimum element in a set without using explicit loops.

    Args:
        input_set: The input set.

    Returns:
        The minimum element in the set, or None if the set is empty.
        Raises TypeError if the set contains elements of mixed comparable types.

    Raises:
        TypeError: If the set contains elements of mixed comparable types
                   (e.g., integers and strings).

    Examples:
        >>> find_minimum_element({1, 2, 3, 4, 5})
        1
        >>> find_minimum_element(set())
        None
    """
    <los>...</los>
    <sol>
    if not input_set:  # Check for empty set
        return None

    else:
      return min(input_set) # Use the built-in min() function
    </sol>

def combined_list_operations(lst: list) -> list:
    """
    Performs a combination of list operations:
    1. Extracts the first and last three elements (or all available if fewer than 3).
    2. Reverses the extracted first elements.
    3. Takes every other element from the reversed first elements.
    4. Takes every other element from the last elements.
    5. Concatenates the results.

    Args:
        lst: The input list.

    Returns:
        A new list with the combined operations applied.

    Example:
    Input: 
    combined_list_operations([1, 2, 3, 4, 5, 6, 7, 8, 9])
    Output:
    [3, 1, 7, 9]
    """
    <los>...</los>
    <sol>
    n = len(lst)
    first_three = lst[:3]
    last_three = lst[-3:]

    reversed_first = first_three[::-1]
    every_other_first = reversed_first[::2]

    every_other_last = last_three[::2]

    return every_other_first + every_other_last
    </sol>


def quadratic_solution_positive(a: float, b: float, c: float) -> float:
    '''
    Given three coefficients of a quadratic equation, return the positive solution.

    Arguments:
    a: float - the coefficient of x^2
    b: float - the coefficient of x
    c: float - the constant term

    Return:
    float - the positive solution

    Example:
    Input : a = 1, b = -5, c = 6
    Output : 3.0
    '''
    <los>...</los>
    <sol>
    return (-b + (b**2 - 4*a*c)**0.5) / (2*a)
    </sol>


def arithmetic_operations(t: tuple) -> tuple:
    '''
    Given a tuple of two integers (a, b), return a tuple containing the 
    product, floor division, exponentiation, and remainder of the two numbers.

    Arguments:
    t: tuple - a tuple of two integers (a, b)

    Return:
    tuple - product, floor division, exponentiation, and remainder of the two numbers.

    Example:
    >>> arithmetic_operations((1, 2))
    (2, 0, 1, 1)
    '''
    <los>...</los>
    <sol>
    a, b = t
    return (a*b, a//b, a**b, a%b)
    </sol>


def reverse_interleave(s: str) -> str:
    '''
    Given a string, return a string with the characters interleaved in reverse order.

    Arguments:
    s: str - the input string

    Return:
    str - the string with the characters interleaved in reverse order.

    Example:
    Input : s = "abcdef"
    Output : "fdbeca"
    '''
    <los>...</los>
    <sol>
    return s[::-2] + s[-2::-2]
    </sol>


def flip_transform_dict(d: dict) -> dict:
    '''
    Given a dictionary, return a dictionary with the keys and values flipped.

    Arguments:
    d: dict - the input dictionary

    Return:
    dict - the dictionary with the keys and values flipped.

    Example:
    Input : d = {"a": 1, "b": 2}
    Output : {1: "a", 2: "b"}    
    '''
    <los>...</los>
    <sol>
    x = d.keys()
    y = d.values()
    return dict(zip(y, x))
    </sol>


def simple_list_operations(lst: list) -> list:
    """
    Performs a sequence of simple list operations using slicing, concatenation, and if/else:

    1. Extracts the first two and last two elements (or all available if fewer).
    2. "Appends" the string "END" to the extracted first elements.
    3. "Inserts" the string "START" at the beginning of the extracted first elements.
    4. "Extends" the extracted last elements with the list ['A', 'B'].
    5. Concatenates all results.
    6. Returns the resulting list.

    Args:
        lst: The input list.

    Returns:
        A new list with the operations applied.

    Example:
    Input:
    >>> simple_list_operations([1, 2, 3, 4, 5])
    Output:
    ['START', 1, 2, 'END', 4, 5, 'A', 'B']
    """
    <los>...</los>
    <sol>
    first_two = lst[:2]
    last_two = lst[-2:]

    appended_first = first_two + ["END"]
    inserted_first = ["START"] + appended_first

    extended_last = last_two + ['A', 'B']

    return inserted_first + extended_last
    </sol>


def swap_digits(n: int) -> int | str:
    """
    Swaps the digits of a two-digit integer, including negative numbers.

    Args:
        n: The two-digit integer.

    Returns:
        The integer with digits swapped.
        Returns an error message string if the input is not a two-digit number.

    Example:
    Input:
    >>> swap_digits(12)
    Output:
    21
    
    >>> swap_digits(90)
    9
    >>> swap_digits(-12)
    -21
    >>> swap_digits(100)
    Input must be a two-digit number
    """
    <los>...</los>
    <sol>
    sign = -1 if n < 0 else 1
    n = abs(n)  # Work with the absolute value

    if not 10 <= n <= 99:
        return "Input must be a two-digit number"

    tens_digit = n // 10
    ones_digit = n % 10

    return sign * ((ones_digit * 10) + tens_digit)
    </sol>
    
</template>

<suffix_invisible>
{% include './function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
is_equal(
    find_minimum_element({1,2,5,6,7}),
    1
)

lst = [1, 2, 3, 4, 5, 6, 7, 8, 9]
is_equal(
    combined_list_operations(lst),
    [3, 1, 7, 9]
)

is_equal(
    quadratic_solution_positive(1, -5, 6),
    3.0
)

is_equal(
    arithmetic_operations((6, 3)),
    (18, 2, 216, 0)
)

is_equal(
    reverse_interleave('abcdef'),
    'fdbeca'
)

is_equal(
    flip_transform_dict({'a': 1, 'b': 2}),
    {1: 'a', 2: 'b'}
)

lst2 = [1, 2, 3, 4, 5]
is_equal(
    simple_list_operations(lst2),
    ['START', 1, 2, 'END', 4, 5, 'A', 'B']
)

is_equal(
    swap_digits(12),
    21
)
```

## Output 1

```
1
[3, 1, 7, 9]
3.0
(18, 2, 216, 0)
'fdbeca'
{1: 'a', 2: 'b'}
['START', 1, 2, 'END', 4, 5, 'A', 'B']
21
```

# Private Test Cases

## Input 1

```
is_equal(
    find_minimum_element(set()),
    None
)

lst = [10, 20, 30, 40, 50, 60]
is_equal(
    combined_list_operations(lst),
    [30, 10, 40, 60]
)

is_equal(
    quadratic_solution_positive(1, -3, 2),
    2.0
)

is_equal(
    arithmetic_operations((5, 2)),
    (10, 2, 25, 1)
)

is_equal(
    reverse_interleave('1234567'),
    '7531642'
)

is_equal(
    flip_transform_dict({'x': 10, 'y': 20, 'z': 30}),
    {10: 'x', 20: 'y', 30: 'z'}
)

lst2 = [10, 20]
is_equal(
    simple_list_operations(lst2),
    ['START', 10, 20, 'END', 10, 20, 'A', 'B']
)

is_equal(
    swap_digits(-34),
    -43
)
```

## Output 1

```
None
[30, 10, 40, 60]
2.0
(10, 2, 25, 1)
'7531642'
{10: 'x', 20: 'y', 30: 'z'}
['START', 10, 20, 'END', 10, 20, 'A', 'B']
-43
```