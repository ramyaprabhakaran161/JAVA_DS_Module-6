# Ex4 You are given a Java program that performs matrix addition. If Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension, what will be the nature (even/odd/mixed) of the resulting matrix?
## DATE:23.3.26
## AIM:
To write a java function to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix.

## Algorithm
~~~
1.Start the program.
2.Read the dimensions of the matrices.
3.Read elements of Matrix A (odd numbers) and Matrix B (even numbers).
4.Perform matrix addition and store the result in Matrix C.
5.Check whether all elements in Matrix C are even, odd, or mixed.
6.Display the resulting matrix and its nature.
7.Stop the program.
~~~

## Program:
```

Developed by: Ramya P
RegisterNumber:  212223230168
```
```

import java.util.Scanner;

public class MatrixNature {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of rows: ");
        int rows = sc.nextInt();
        System.out.print("Enter number of columns: ");
        int cols = sc.nextInt();

        int[][] A = new int[rows][cols];
        int[][] B = new int[rows][cols];
        int[][] C = new int[rows][cols];

        System.out.println("Enter elements of Matrix A (odd numbers):");
        for (int i = 0; i < rows; i++)
            for (int j = 0; j < cols; j++)
                A[i][j] = sc.nextInt();

        System.out.println("Enter elements of Matrix B (even numbers):");
        for (int i = 0; i < rows; i++)
            for (int j = 0; j < cols; j++)
                B[i][j] = sc.nextInt();

        System.out.println("Resultant Matrix (A + B):");
        String nature = "";
        boolean allEven = true, allOdd = true;

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                C[i][j] = A[i][j] + B[i][j];
                System.out.print(C[i][j] + " ");
                if (C[i][j] % 2 == 0)
                    allOdd = false;
                else
                    allEven = false;
            }
            System.out.println();
        }

        if (allEven)
            nature = "Even";
        else if (allOdd)
            nature = "Odd";
        else
            nature = "Mixed";

        System.out.println("Nature of resultant matrix: " + nature);
        sc.close();
    }
}
```


## Output:

<img width="955" height="452" alt="image" src="https://github.com/user-attachments/assets/77f1b55f-4224-4d00-9c94-addd829d0334" />


## Result:
Thus, the java program to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix is implemented successfully.
