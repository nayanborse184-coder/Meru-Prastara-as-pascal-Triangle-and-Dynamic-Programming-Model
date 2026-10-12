# Meru-Prastara-as-pascal-Triangle-and-Dynamic-Programming-Model
Meru Prastara (Pascal’s Triangle) using Dynamic Programming to explore ancient Indian mathematics, recurrence relations, binomial coefficients, and efficient algorithm design. A simple educational project connecting traditional mathematical concepts with modern computer science.

# Meru--prastara-as-pascal-Triangle-and-Dynamic-Programming-Model-
Meru Prasthara (Pascal’s Triangle) using Dynamic ProgrammingThis project demonstrates Meru Prasthara, also known as Pascal’s Triangle, using Dynamic Programming to generate its rows. Each number is calculated by adding the two numbers directly above it, illustrating the concept of reusing previously computed values to solve problems efficiently.


Meru-Prastara as Pascal's Triangle and Dynamic Programming Model

1. Introduction

Meru-Prastara is an ancient Indian mathematical arrangement that is closely related to Pascal's Triangle. This project explores the relationship between Meru-Prastara and modern Computer Science concepts, especially Dynamic Programming.

Pascal's Triangle is a triangular arrangement of numbers in which each row begins and ends with 1. Every inner number is calculated by adding the two numbers directly above it.

This project implements Meru-Prastara using Python and demonstrates how previously calculated values can be stored and reused to generate the next row efficiently.

The project connects the Indian Knowledge System (IKS) with modern programming concepts such as algorithms, recurrence relations, lists, and Dynamic Programming.

2. Problem Statement

The objective of this project is to design and implement a Python program that generates the first "n" rows of Meru-Prastara, also known as Pascal's Triangle.

The program follows these rules:

- Every row starts and ends with 1.
- Each inner element is calculated by adding the two adjacent elements from the previous row.
- Previously calculated rows are stored and reused.
- The program validates input and handles invalid values appropriately.

3. Objectives

- To understand the mathematical structure of Meru-Prastara.
- To explore its relationship with Pascal's Triangle.
- To implement the triangle using Python.
- To demonstrate Dynamic Programming through stored and reused results.
- To understand recurrence relations and nested lists.
- To analyze the time and space complexity of the algorithm.
- To connect traditional Indian mathematical knowledge with Computer Science.

4. Concepts Used

Meru-Prastara

An ancient Indian mathematical arrangement associated with combinatorial patterns and prosody.

Pascal's Triangle

A triangular arrangement in which each inner number is the sum of the two numbers directly above it.

Dynamic Programming

A programming technique in which previously computed results are stored and reused to solve larger problems.

Recurrence Relation

The relationship used to calculate each inner value:

"triangle[i][j] = triangle[i-1][j-1] + triangle[i-1][j]"

Lists and Nested Lists

Python lists are used to store individual rows, while a list of lists stores the complete triangle.

5. Example of Meru-Prastara / Pascal's Triangle

The first six rows are:

             1
           1   1
         1   2   1
       1   3   3   1
     1   4   6   4   1
   1   5  10  10   5   1

For example, in the row "[1, 3, 3, 1]", the next row becomes "[1, 4, 6, 4, 1]".

The inner values are calculated as follows:

- "1 + 3 = 4"
- "3 + 3 = 6"
- "3 + 1 = 4"

The first and last elements remain 1.

6. Algorithm

1. Accept "n", the number of rows to generate.
2. Check whether "n" is an integer.
3. If "n" is negative, report invalid input.
4. Create an empty list named "triangle".
5. Generate each row with "i + 1" elements initialized to 1.
6. Calculate inner elements using the two adjacent elements from the previous row.
7. Append the completed row to "triangle".
8. Return the complete triangle.
9. Display the triangle in a readable format.

7. Python Implementation

def generate_meru_prastara(n):
    """Generate n rows of Meru-Prastara (Pascal's Triangle)."""

    if not isinstance(n, int) or isinstance(n, bool):
        raise TypeError("n must be an integer")

    if n < 0:
        raise ValueError("n must be non-negative")

    triangle = []

    for i in range(n):
        row = [1] * (i + 1)

        for j in range(1, i):
            row[j] = (
                triangle[i - 1][j - 1]
                + triangle[i - 1][j]
            )

        triangle.append(row)

    return triangle


def print_meru_prastara(n):
    triangle = generate_meru_prastara(n)

    if n == 0:
        print("(empty triangle)")
        return

    width = len(" ".join(map(str, triangle[-1])))

    for row in triangle:
        text = " ".join(map(str, row))
        print(text.center(width))


if __name__ == "__main__":
    n = 6
    print_meru_prastara(n)

8. Sample Output

For input "n = 6", the program generates six rows:

             1
            1 1
           1 2 1
          1 3 3 1
        1 4 6 4 1
      1 5 10 10 5 1

The exact spacing may vary depending on the terminal.

9. Test Cases

The following test cases cover normal inputs, boundary cases, larger inputs, and invalid inputs.

Test No.| Input| Expected Result
1| "0"| Empty triangle "[]"
2| "1"| "[[1]]"
3| "2"| "[[1], [1, 1]]"
4| "3"| "[[1], [1, 1], [1, 2, 1]]"
5| "4"| Last row: "[1, 3, 3, 1]"
6| "5"| Last row: "[1, 4, 6, 4, 1]"
7| "6"| Last row: "[1, 5, 10, 10, 5, 1]"
8| "10"| Generates 10 rows
9| "15"| Generates 15 rows
10| "20"| Generates 20 rows
11| "-1"| Raises "ValueError"
12| "3.5"| Raises "TypeError"

10. Dynamic Programming Explanation

Dynamic Programming is demonstrated by storing previously generated rows in the "triangle" list.

When a new row is generated, its inner values are calculated using the previous row instead of calculating each value independently from scratch.

For example:

Previous row:

"[1, 3, 3, 1]"

Next row:

"[1, 4, 6, 4, 1]"

The program reuses the stored values to calculate the new row.

This demonstrates the Dynamic Programming principle of solving smaller subproblems, storing their results, and reusing them to solve larger problems.

11. Complexity Analysis

Time Complexity: O(n²)

For "n" rows, the total number of generated elements is:

"1 + 2 + 3 + ... + n = n(n + 1) / 2"

Therefore, the time complexity is "O(n²)".

Space Complexity: O(n²)

The complete triangle is stored in memory as a nested list. Therefore, the space complexity is "O(n²)".

If only the latest row were required, the storage requirement could be reduced to "O(n)" with a different implementation.

12. Limitations

- The complete triangle requires quadratic memory as the number of rows increases.
- Very large rows may contain numbers with many digits, increasing computation and memory requirements.
- A large triangle is difficult to display clearly in a terminal.
- This implementation focuses on generating the triangle and does not cover every application of Meru-Prastara in ancient Indian prosody.
- The program accepts the number of rows as input rather than answering a specific combinatorial query.

13. Conclusion

This project demonstrates how Meru-Prastara can be studied in relation to Pascal's Triangle and modern Dynamic Programming.

The Python implementation generates the triangle by storing previously calculated rows and reusing their values to construct subsequent rows.

Through this project, important Computer Science concepts such as recurrence relations, nested lists, algorithm design, Dynamic Programming, and computational complexity can be understood through a mathematical pattern connected with the Indian Knowledge System.

14. Technologies Used

- Programming Language: Python
- Core Concept: Dynamic Programming
- Data Structure: Lists and nested lists
- Mathematical Model: Meru-Prastara / Pascal's Triangle

15. Author

Nayan Borse

B.Sc. Computer Science — Semester V
Smt. Devkiba Mohansinhji Chauhan College of Commerce and Science, Silvassa

Academic Year: 2026–2027

16. References

- Indian Knowledge Systems (IKS) — introductory material on traditional Indian mathematics and prosody.
- Standard discrete mathematics references covering binomial coefficients and Pascal's Triangle.
- Standard algorithms and Dynamic Programming textbooks covering recurrence relations and complexity analysis.
