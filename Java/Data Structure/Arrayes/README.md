# Arrayes
## Declaration
```cpp
char[] arr = {'a', 'b', 'c'};
```

```cpp
Scanner input = new Scanner(System.in);

int [] arr = new int[5];
for(int i = 0; i < arr.length; i++){
    arr[i] = input.nextInt();
}

for(int num : arr){
    System.out.print(num + " ");
}
```

## Array with methods
```c++
import java.util.Scanner;

public class Main {
    static void printArray(int []arr) {
        for (int i : arr)
            System.out.print(i + " ");
    }

    static int[] getArray() {
        int arr[] = {1, 2, 3};
        return arr;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4};

        System.out.println("First Arr: ");
        printArray(arr);

        int[] returnedArray = getArray();
        System.out.println("\nSecond Arr: ");
        for(int i : returnedArray)
            System.out.print(i + " ");
    }
}
```
## Array assigned by reference
```cpp
int []arr = new int[]{1,2,3};
int []arr2 = arr; // arr2 refers to the same location of arr 1 [reference]
arr2[0] = 5;
System.out.println(arr[0]); //5
```
## Arrays are passed by reference
```cpp
static void updateArray(int []arr){
    arr[0] = 5;
}
public static void main(String[] args) {
    int []arr = new int[]{1,2,3};
    updateArray(arr); // updating by reference
    System.out.println(arr[0]); // 5
}
```
