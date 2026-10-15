````markdown

# Quick Sort

## Question 1

**Problem:**  
Write a Java program to sort an array in ascending order using the Quick Sort algorithm.

### Java Code

```java
package ds_pro;

import java.util.Arrays;

public class quickSort {

    public static int partition(int[] arr, int low, int high) {

        int pivot = high;
        int j = low - 1;

        for (int i = low; i <= high; i++) {

            if (arr[i] <= arr[pivot]) {

                j++;

                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        return j;
    }

    public static void quicksort(int[] arr, int low, int high) {

        if (low < high) {

            int pivot = partition(arr, low, high);

            quicksort(arr, low, pivot - 1);
            quicksort(arr, pivot + 1, high);
        }
    }

    public static void main(String[] args) {

        int[] arr = {5, 8, 7, 6, 9, 1, 2, 3, 4};

        System.out.println("Before Sorting: " + Arrays.toString(arr));

        quicksort(arr, 0, arr.length - 1);

        System.out.println("After Sorting: " + Arrays.toString(arr));
    }
}
```

### Sample Output

```text
Before Sorting: [5, 8, 7, 6, 9, 1, 2, 3, 4]
After Sorting: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

````
````markdown
# Merge Sort

## Question 2

**Problem:**  
Write a Java program to sort an array in ascending order using the Merge Sort algorithm.

### Java Code

```java
package ds_pro;

import java.util.Arrays;

public class mergeSort {

    public static void divide(int[] arr, int low, int high) {

        if (low < high) {

            int mid = (low + high) / 2;

            divide(arr, low, mid);       // Left half
            divide(arr, mid + 1, high);  // Right half

            merge(arr, low, mid, high);
        }
    }

    public static void merge(int[] arr, int low, int mid, int high) {

        int[] temp = new int[high - low + 1];

        int left = low;
        int right = mid + 1;
        int index = 0;

        while (left <= mid && right <= high) {

            if (arr[left] <= arr[right]) {
                temp[index] = arr[left];
                left++;
            } else {
                temp[index] = arr[right];
                right++;
            }

            index++;
        }

        while (left <= mid) {
            temp[index++] = arr[left++];
        }

        while (right <= high) {
            temp[index++] = arr[right++];
        }

        for (int i = 0; i < temp.length; i++) {
            arr[low + i] = temp[i];
        }
    }

    public static void main(String[] args) {

        int[] arr = {5, 8, 7, 6, 9, 1, 2, 3, 4};

        System.out.println("Before Sorting: " + Arrays.toString(arr));

        divide(arr, 0, arr.length - 1);

        System.out.println("After Sorting: " + Arrays.toString(arr));
    }
}
```

### Sample Output

```text
Before Sorting: [5, 8, 7, 6, 9, 1, 2, 3, 4]
After Sorting: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

````
````markdown

````
````markdown

````
````markdown

````
````markdown

````
````markdown

````
````markdown

