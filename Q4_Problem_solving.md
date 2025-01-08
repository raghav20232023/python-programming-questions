---
title: Application Development type question with multiple functions
tags: ['dictionaries', 'functions', 'function-application']
---

# Problem Statement
Implement the given application according to the docstrings.
Details about the application to be implemented are given as follows:
def add_grades(student_grades, student, grades):
    """
    Adds grades for a student.

    Parameters:
        student_grades (dict): Dictionary with student names as keys and lists of grades as values.
        student (str): Name of the student.
        grades (list of int): Grades to add for the student.

    Returns:
        dict: Updated student_grades dictionary.

    Example:
        student_grades = {}
        add_grades(student_grades, "Alice", [85, 90])
        # student_grades becomes {"Alice": [85, 90]}
    """

# Solution
```py3 test.py  -r 'python test.py'
<prefix>
</prefix>
<template>
def add_grades(student_grades, student, grades):
    """
    Adds grades for a student.

    Parameters:
        student_grades (dict): Dictionary with student names as keys and lists of grades as values.
        student (str): Name of the student.
        grades (list of int): Grades to add for the student.

    Returns:
        dict: Updated student_grades dictionary.

    Example:
        student_grades = {}
        add_grades(student_grades, "Alice", [85, 90])
        # student_grades becomes {"Alice": [85, 90]}
    """
    <los>...</los>
    <sol>
    if student not in student_grades:
        student_grades[student] = []
    student_grades[student].extend(grades)
    return student_grades
    </sol>

def calculate_average(student_grades, student):
    """
    Calculates the average grade of a student.

    Parameters:
        student_grades (dict): Dictionary with student names as keys and lists of grades as values.
        student (str): Name of the student.

    Returns:
        float: Average grade of the student. Returns 0.0 if the student does not exist.

    Example:
        student_grades = {"Alice": [85, 90]}
        calculate_average(student_grades, "Alice")
        # Returns: 87.5
    """
    <los>...</los>
    <sol>
    if student in student_grades and student_grades[student]:
        total = sum(student_grades[student])
        count = len(student_grades[student])
        return total / count
    return 0.0
    </sol>

def find_top_student(student_grades):
    """
    Finds the student with the highest average grade.

    Parameters:
        student_grades (dict): Dictionary with student names as keys and lists of grades as values.

    Returns:
        str: Name of the student with the highest average grade. Returns "No students" if the dictionary is empty.

    Example:
        student_grades = {"Alice": [85, 90], "Bob": [70, 80]}
        find_top_student(student_grades)
        # Returns: "Alice"
    """
    <los>...</los>
    <sol>
    top_student = None
    highest_average = 0.0

    for student in student_grades:
        avg = calculate_average(student_grades, student)
        if avg > highest_average:
            highest_average = avg
            top_student = student

    return top_student if top_student else "No students"
    </sol>
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
student_grades = {"Alice": [85, 90], "Bob": [70, 80]}
is_equal(
    calculate_average(student_grades, "Alice"),
    87.5
)
```

## Output 1

```
87.5
```

## Input 2

```
student_grades = {"Alice": [85, 90], "Bob": [70, 80]}
is_equal(
    find_top_student(student_grades),
    'Alice'
)
```

## Output 2

```
'Alice'
```

# Private Test Cases

## Input 1

```
student_grades = {"Trevor": [85], "Joey": [100]}
is_equal(
    find_top_student(student_grades),
    'Joey'
)
```

## Output 1

```
'Joey'
```
