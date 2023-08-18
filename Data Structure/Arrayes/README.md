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
