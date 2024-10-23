# BinarySearch:
```csharp
 // Binary search works by dividing an array in half and comparing the middle to the target
 // It will do this multiple times until the middle is the target
 // Requires the array to be sorted already
 static int BinarySearch(int[] array, int target) {
     // init left and right
     int left = 0;
     int right = array.Length - 1;
     int middle;

     while (left <= right) {
         // middle is index total divided by 2
         middle = (left+right) / 2;

         // Debug to see middle update as it cycles
         Console.WriteLine($"middle index = {middle}, middle value = {array[middle]}");

         // Check if middle is target
         if (array[middle] == target) {
             return middle;
         // If middle is smaller then target make left index middle + 1
         }else if (array[middle] < target) {
             left = middle + 1;
         } else { // if middle is larger then target then make right index middle - 1
             right = middle - 1;
         }

     }

     // Return -1 if target not found
     return -1;
 }
```

# BubbleSort:
```csharp
static void BubbleSort(int[] array) {
    int temp;

    // Loop through array
    for (int a = 0; a < array.Length; a++) {
        // Compare each element in array to adjacent values
        for (int b = 0; b < array.Length; b++) {
            // Swap element if element value is smaller
            if (array[a] < array[b]) {
                temp = array[a];
                array[a] = array[b];
                array[b] = temp;
            }
        }
    }
}
```


# Overall:
```csharp
namespace BinarySearchDemo {
    internal class Program {

        // Binary search work by dividing an array in half and comparing the middle to the target
        // It will do this multiple times until the middle is the target
        // Requires the array to be sorted already
        static int BinarySearch(int[] array, int target) {
            // init left and right
            int left = 0;
            int right = array.Length - 1;
            int middle;

            while (left <= right) {
                // middle is index total divided by 2
                middle = (left+right) / 2;

                // Debug to see middle update as it cycles
                Console.WriteLine($"middle index = {middle}, middle value = {array[middle]}");

                // Check if middle is target
                if (array[middle] == target) {
                    return middle;
                // If middle is smaller then target make left index middle + 1
                }else if (array[middle] < target) {
                    left = middle + 1;
                } else { // if middle is larger then target then make right index middle - 1
                    right = middle - 1;
                }

            }

            // Return -1 if target not found
            return -1;
        }

        static void BubbleSort(int[] array) {
            int temp;

            // Loop through array
            for (int a = 0; a < array.Length; a++) {
                // Compare each element in array to adjacent values
                for (int b = 0; b < array.Length; b++) {
                    // Swap element if element value is smaller
                    if (array[a] < array[b]) {
                        temp = array[a];
                        array[a] = array[b];
                        array[b] = temp;
                    }
                }
            }

        }


        static void Main(string[] args) {
            int[] numbers = { 18, 5, 13, 7, 2, 15, 11, 1, 14, 9, 4, 16, 10, 19, 6, 12, 8, 3, 17, 20 };

            Console.WriteLine("Original array: ");
            foreach (int number in numbers) {
                Console.Write($"{number} ");
            }

            Console.WriteLine("\n\nBubbleSorted array: ");
            BubbleSort(numbers);
            foreach (int number in numbers) {
                Console.Write($"{number} ");
            }

            Console.WriteLine("\n\nBinarySearch for 3: ");
            Console.Write($"Located at index: {BinarySearch(numbers, 3)}");

            Console.WriteLine("\n\nBinarySearch for 17: ");
            Console.Write($"Located at index: {BinarySearch(numbers, 17)}");

            Console.WriteLine("\n\nBinarySearch for 30: ");
            Console.Write($"Located at index: {BinarySearch(numbers, 30)}");

            Console.WriteLine("\n\n");
        }
    }
}

```
