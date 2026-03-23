# EX 1 You’re creating a health monitoring device which stores several sensor readings in an array. To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
## DATE:23.3.26
## AIM:
To write a JAVA program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.

## Algorithm
~~~
1.Start the program.
2.Read the number of elements and store them in an array.
3.Define a recursive function findMin() that compares elements to find the minimum.
4.Base condition: If the array has one element, return that element.
5.Recursive step: Compare the last element with the minimum of the rest of the array and return the smaller one.
6.Display the minimum value.
7.Stop the program.
~~~

## Program:
```
Name:Ramya P
Register No:212223230168
```
```
import java.util.Scanner;

public class MinValueRecursive {
    static int findMin(int arr[], int n) {
        if (n == 1)
            return arr[0];
        return Math.min(arr[n - 1], findMin(arr, n - 1));
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of readings: ");
        int n = sc.nextInt();
        int arr[] = new int[n];
        System.out.println("Enter the readings:");
        for (int i = 0; i < n; i++)
            arr[i] = sc.nextInt();
        System.out.println("Minimum value (lowest heartbeat): " + findMin(arr, n));
        sc.close();
    }
}
```

## Output:
<img width="808" height="356" alt="image" src="https://github.com/user-attachments/assets/289b9b67-fbb7-4449-b7a6-906c2f31e9df" />




## Result:
Thus the JAVA prograM ti find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully
