# Ex5 Count Inversions in an Array
## DATE:23.3.26
## AIM:
To write a Java program  to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

## Algorithm
1.Start the program.
2.Read the number of elements and store them in an array.
3.Use a modified merge sort to count inversions:
Recursively split the array into halves and count inversions in each half.
While merging two sorted halves, count cross inversions when an element from the right half is placed before elements remaining in the left half.
4.Sum inversions from left half, right half, and cross inversions.
5.Display the total inversion count.
6.Stop the program

## Program:
```

Developed by: Ramya P
RegisterNumber:212223230168  

```
```

import java.util.Scanner;

public class CountInversions {
    static long mergeCount(int[] arr, int[] temp, int left, int mid, int right) {
        int i = left, j = mid + 1, k = left;
        long invCount = 0;
        while (i <= mid && j <= right) {
            if (arr[i] <= arr[j]) {
                temp[k++] = arr[i++];
            } else {
                temp[k++] = arr[j++];
                invCount += (mid - i + 1);
            }
        }
        while (i <= mid) temp[k++] = arr[i++];
        while (j <= right) temp[k++] = arr[j++];
        for (i = left; i <= right; i++) arr[i] = temp[i];
        return invCount;
    }

    static long mergeSortCount(int[] arr, int[] temp, int left, int right) {
        long invCount = 0;
        if (left < right) {
            int mid = left + (right - left) / 2;
            invCount += mergeSortCount(arr, temp, left, mid);
            invCount += mergeSortCount(arr, temp, mid + 1, right);
            invCount += mergeCount(arr, temp, left, mid, right);
        }
        return invCount;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();
        int[] arr = new int[n];
        System.out.println("Enter the elements:");
        for (int i = 0; i < n; i++) arr[i] = sc.nextInt();
        int[] temp = new int[n];
        long inversions = mergeSortCount(arr, temp, 0, n - 1);
        System.out.println("Number of inversions: " + inversions);
        sc.close();
    }
}
```

## Output:
<img width="872" height="268" alt="image" src="https://github.com/user-attachments/assets/80e69fb8-05ab-4231-a348-bab7f1dde432" />



## Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < jis implemented successfully.
