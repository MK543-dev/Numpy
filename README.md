NUMPY NOTES
===========

1. INTRODUCTION TO NUMPY
------------------------
NumPy = Numerical Python

NumPy is a Python library used for:
    - Numerical calculations
    - Working with arrays
    - Mathematical operations
    - Data analysis
    - Scientific computing
    - Machine Learning

Import NumPy:
    import numpy as np

Here:
    np = commonly used alias for NumPy


2. CREATING NUMPY ARRAYS
------------------------

2.1 np.array()
--------------
Used to create a NumPy array.

Example:
    import numpy as np

    a = np.array([10, 20, 30, 40])

    print(a)

Output:
    [10 20 30 40]


2D Array:
    a = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

Output:
    [[1 2 3]
     [4 5 6]]

A 2D array contains:
    - Rows
    - Columns


3. np.arange()
--------------

Used to create a sequence of numbers.

Syntax:
    np.arange(start, stop, step)

Example:
    np.arange(1, 10)

Output:
    [1 2 3 4 5 6 7 8 9]

Important:
    - Start value is included
    - Stop value is excluded

Example:
    np.arange(1, 10, 2)

Output:
    [1 3 5 7 9]


4. np.zeros()
-------------

Creates an array containing zeros.

Example:
    np.zeros(5)

Output:
    [0. 0. 0. 0. 0.]

2D array:
    np.zeros((2, 3))

Output:
    [[0. 0. 0.]
     [0. 0. 0.]]

Meaning:
    2 rows × 3 columns


5. np.ones()
------------

Creates an array containing ones.

Example:
    np.ones(5)

Output:
    [1. 1. 1. 1. 1.]

2D array:
    np.ones((2, 3))

Output:
    [[1. 1. 1.]
     [1. 1. 1.]]


6. np.linspace()
----------------

Creates evenly spaced numbers between two values.

Syntax:
    np.linspace(start, stop, number_of_values)

Example:
    np.linspace(1, 10, 5)

Output:
    [1.    3.25  5.5   7.75 10. ]

Difference:

    arange()
        -> Specifies the step size

    linspace()
        -> Specifies the number of values


7. RANDOM NUMBERS
-----------------

7.1 np.random.rand()
--------------------
Generates random numbers between 0 and 1.

Example:
    np.random.rand(5)

Example output:
    [0.25 0.71 0.13 0.91 0.42]


7.2 np.random.randn()
---------------------
Generates random numbers using a standard normal distribution.

Example:
    np.random.randn(5)

Example output:
    [ 0.42 -1.12  0.33 -0.75  1.21]


7.3 np.random.randint()
----------------------
Generates random integers.

Syntax:
    np.random.randint(start, stop)

Example:
    np.random.randint(1, 10)

Example output:
    7

Generate multiple random integers:
    np.random.randint(1, 10, 5)

Example output:
    [3 8 1 6 4]


8. RESHAPE
----------

reshape() is used to change the shape of an array.

Example:
    a = np.arange(1, 7)

    print(a)

Output:
    [1 2 3 4 5 6]

Now reshape:
    a.reshape(2, 3)

Output:
    [[1 2 3]
     [4 5 6]]

Important Rule:
    Total number of elements must remain the same.

Example:
    6 elements

    2 × 3 = 6     VALID
    3 × 2 = 6     VALID
    1 × 6 = 6     VALID
    2 × 4 = 8     INVALID


9. ARRAY PROPERTIES
-------------------

Consider:
    a = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])


9.1 shape
---------
Returns the number of rows and columns.

Example:
    a.shape

Output:
    (2, 3)

Meaning:
    2 rows
    3 columns


9.2 size
--------
Returns the total number of elements.

Example:
    a.size

Output:
    6


9.3 dtype
---------
Returns the data type of the elements.

Example:
    a.dtype

Example output:
    int64


10. ARRAY STATISTICS
--------------------

Example:
    a = np.array([10, 20, 30, 40, 50])


10.1 min()
----------
Returns the smallest value.

    a.min()

Output:
    10


10.2 max()
----------
Returns the largest value.

    a.max()

Output:
    50


10.3 sum()
----------
Returns the total of all elements.

    a.sum()

Output:
    150


10.4 mean()
-----------
Returns the average.

    a.mean()

Output:
    30

Formula:
    Mean = Sum of values / Number of values


10.5 std()
----------
std() means Standard Deviation.

It measures how much the values are spread out.


11. argmin() AND argmax()
-------------------------

These functions return the INDEX of the minimum or maximum value.

Example:
    a = np.array([50, 20, 80, 10, 40])

Indexes:
    Index:   0   1   2   3   4
    Value:  50  20  80  10  40


11.1 argmin()
-------------
Returns the index of the smallest value.

    a.argmin()

Output:
    3

Because:
    Minimum value = 10
    Index = 3


11.2 argmax()
-------------
Returns the index of the largest value.

    a.argmax()

Output:
    2

Because:
    Maximum value = 80
    Index = 2


12. AXIS
--------

Axis is very important in NumPy.

Consider:
    a = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])


12.1 axis=0
------------
Works column-wise.

    a.sum(axis=0)

Output:
    [50 70 90]

Calculation:
    10 + 40 = 50
    20 + 50 = 70
    30 + 60 = 90


12.2 axis=1
------------
Works row-wise.

    a.sum(axis=1)

Output:
    [60 150]

Calculation:
    10 + 20 + 30 = 60
    40 + 50 + 60 = 150


Easy Memory Trick:
    axis=0 -> Column-wise
    axis=1 -> Row-wise


13. INDEXING
------------

Indexing means accessing a particular element.

Python indexing starts from 0.

Example:
    a = np.array([10, 20, 30, 40])

Indexes:
    Index:   0   1   2   3
    Value:  10  20  30  40

Example:
    a[0]

Output:
    10

Example:
    a[2]

Output:
    30


14. 2D ARRAY INDEXING
---------------------

Example:
    a = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])

Syntax:
    a[row, column]

Example:
    a[0, 1]

Output:
    20

Because:
    Row = 0
    Column = 1


15. SLICING
-----------

Slicing is used to extract a part of an array.

Example:
    a = np.array([10, 20, 30, 40, 50])

    a[1:4]

Output:
    [20 30 40]

Syntax:
    array[start:stop]

Important:
    Start is included.
    Stop is excluded.


16. REVERSE SLICING
-------------------

To reverse an array:

    a[::-1]

Example:
    a = np.array([10, 20, 30, 40, 50])

    a[::-1]

Output:
    [50 40 30 20 10]


17. JOINING ARRAYS
------------------

17.1 np.hstack()
----------------
hstack means Horizontal Stack.

Example:
    a = np.array([1, 2, 3])
    b = np.array([4, 5, 6])

    np.hstack((a, b))

Output:
    [1 2 3 4 5 6]


17.2 np.column_stack()
----------------------
Combines arrays as columns.

Example:
    a = np.array([1, 2, 3])
    b = np.array([4, 5, 6])

    np.column_stack((a, b))

Output:
    [[1 4]
     [2 5]
     [3 6]]


18. SPLITTING ARRAYS
--------------------

18.1 np.hsplit()
----------------
Splits an array horizontally.

Example:
    a = np.arange(1, 7).reshape(2, 3)

Array:
    [[1 2 3]
     [4 5 6]]


18.2 np.vsplit()
----------------
Splits an array vertically.

Example:
    np.vsplit(a, 2)

It divides the array based on rows.


19. ITERATING THROUGH ARRAYS
----------------------------

For a 1D array:

    a = np.array([10, 20, 30])

    for x in a:
        print(x)

Output:
    10
    20
    30


For a 2D array:

    for row in a:
        print(row)

Each row is processed separately.


20. BOOLEAN FILTERING
---------------------

Boolean filtering is used to select values based on conditions.

Example:
    marks = np.array([65, 90, 75, 95, 60])

Find marks greater than 80:

    marks[marks > 80]

Output:
    [90 95]

This is called:
    Boolean Indexing
    OR
    Boolean Filtering


21. MODIFYING ARRAY VALUES
--------------------------

Example:
    marks = np.array([60, 70, 80, 90])

Add 5 to every mark:

    marks = marks + 5

Result:
    [65 75 85 95]


Modify values using a condition:

    marks[marks < 75] = 0

This replaces every value below 75 with 0.


22. PRACTICAL EXERCISE - STUDENT DATA
--------------------------------------

Example data:

    Age    Math    Science
    18     85      90
    19     92      88
    18     75      70
    20     95      82


Find average age:

    students[:, 0].mean()


Find maximum Science mark:

    students[:, 2].max()


Find students with Math marks greater than 90:

    students[students[:, 1] > 90]


Find students younger than 19:

    students[students[:, 0] < 19]


Increase Math marks by 5:

    students[:, 1] += 5


Count students younger than 19:

    np.sum(students[:, 0] < 19)


Find students with Math and Science marks >= 80:

    students[
        (students[:, 1] >= 80) &
        (students[:, 2] >= 80)
    ]


23. SUDOKU-STYLE ARRAY VALIDATION
---------------------------------

A Sudoku board is a 9 × 9 array.

NumPy can be used to check:
    - Row values
    - Column values
    - 3 × 3 blocks


Check row sums:

    np.sum(board, axis=1)


Check column sums:

    np.sum(board, axis=0)


Sudoku structure:

    ┌─────────┬─────────┬─────────┐
    │ 3 × 3   │ 3 × 3   │ 3 × 3   │
    ├─────────┼─────────┼─────────┤
    │ 3 × 3   │ 3 × 3   │ 3 × 3   │
    ├─────────┼─────────┼─────────┤
    │ 3 × 3   │ 3 × 3   │ 3 × 3   │
    └─────────┴─────────┴─────────┘


24. IMPORTANT NUMPY FUNCTIONS
-----------------------------

    np.array()
        -> Creates an array

    np.arange()
        -> Creates a sequence

    np.zeros()
        -> Creates an array of zeros

    np.ones()
        -> Creates an array of ones

    np.linspace()
        -> Creates evenly spaced numbers

    np.random.rand()
        -> Random decimal numbers

    np.random.randn()
        -> Random numbers from normal distribution

    np.random.randint()
        -> Random integers

    reshape()
        -> Changes array shape

    shape
        -> Returns rows and columns

    size
        -> Returns total elements

    dtype
        -> Returns data type

    min()
        -> Minimum value

    max()
        -> Maximum value

    sum()
        -> Sum of values

    mean()
        -> Average

    std()
        -> Standard deviation

    argmin()
        -> Index of minimum value

    argmax()
        -> Index of maximum value

    np.hstack()
        -> Horizontal joining

    np.column_stack()
        -> Joins arrays as columns

    np.hsplit()
        -> Horizontal splitting

    np.vsplit()
        -> Vertical splitting


25. QUICK REVISION
------------------

NumPy
    |
    |-- Array Creation
    |     |-- np.array()
    |     |-- np.arange()
    |     |-- np.zeros()
    |     |-- np.ones()
    |     |-- np.linspace()
    |
    |-- Random
    |     |-- rand()
    |     |-- randn()
    |     |-- randint()
    |
    |-- Properties
    |     |-- shape
    |     |-- size
    |     |-- dtype
    |
    |-- Statistics
    |     |-- min()
    |     |-- max()
    |     |-- sum()
    |     |-- mean()
    |     |-- std()
    |     |-- argmin()
    |     |-- argmax()
    |
    |-- Manipulation
    |     |-- reshape()
    |     |-- hstack()
    |     |-- column_stack()
    |     |-- hsplit()
    |     |-- vsplit()
    |
    |-- Accessing Data
          |-- Indexing
          |-- Slicing
          |-- Boolean Filtering


MOST IMPORTANT:
    axis=0 -> Column-wise
    axis=1 -> Row-wise

    Indexing starts from 0.

    Slicing:
        start -> included
        stop  -> excluded

    reshape():
        Total number of elements must remain the same.
