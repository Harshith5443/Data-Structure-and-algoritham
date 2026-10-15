````markdown

# Quick Sort

## Question 5

**Problem:**  
Write a Java program to sort an array in ascending order using the Quick Sort algorithm.

### Java Code

```java
package ds_pro;

import java.util.Arrays;

public class QuickSort {

    static void quickSort(int[] arr, int low, int high) {

        if (low < high) {

            int pivot = partition(arr, low, high);

            quickSort(arr, low, pivot - 1);
            quickSort(arr, pivot + 1, high);
        }
    }

    static int partition(int[] arr, int low, int high) {

        int pivot = high;
        int i = low - 1;

        for (int j = low; j < high; j++) {

            if (arr[j] < arr[pivot]) {

                i++;

                int temp = arr[j];
                arr[j] = arr[i];
                arr[i] = temp;
            }
        }

        // Place the pivot in its correct position
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }

    public static void main(String[] args) {

        int[] arr = {6, 2, 1, 5, 3, 4};

        quickSort(arr, 0, arr.length - 1);

        System.out.println(Arrays.toString(arr));
    }
}
```

### Sample Output

```text
[1, 2, 3, 4, 5, 6]
```
