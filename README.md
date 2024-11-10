# Task 1 
import java.util.Scanner;
public class Lab4Task1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double[] numbers = new double[7];
        double sum = 0;
        System.out.println("Enter 7 real numbers:");
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = sc.nextDouble();
            sum += numbers[i];
        }
        double mean = sum / numbers.length;
        System.out.println("Sum of all elements: " + sum);
        System.out.println("Mean of all elements: " + mean);
        sc.close();
    }
}

# Task 2
import java.util.Arrays;
import java.util.Scanner;
public class Lab4Task2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double[] numbers = new double[7];
        double sum = 0;
        System.out.println("Enter 7 real numbers:");
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = sc.nextDouble();
            sum += numbers[i];
        }
        double mean = sum / numbers.length;
        System.out.println("Sum of all elements: " + sum);
        System.out.println("Mean of all elements: " + mean);
        System.out.print("Enter a key to split the array: ");
        double key = sc.nextDouble();      
        double[][] splitArrays = splitArrayAtKey(numbers, key);
        if (splitArrays != null) {
            System.out.println("Array before the key (inclusive): " + Arrays.toString(splitArrays[0]));
            System.out.println("Array after the key: " + Arrays.toString(splitArrays[1]));
        } else {
            System.out.println("Key not found in the array.");
        }
        sc.close();
    }
    public static double[][] splitArrayAtKey(double[] array, double key) {
        int keyIndex = -1;
        for (int i = 0; i < array.length; i++) {
            if (array[i] == key) {
                keyIndex = i;
                break;
            }
        }
        if (keyIndex == -1) {
            return null;
        }
        double[] firstPart = Arrays.copyOfRange(array, 0, keyIndex + 1);
        double[] secondPart = Arrays.copyOfRange(array, keyIndex + 1, array.length);
        return new double[][]{firstPart, secondPart};
    }
}

# Task 3
public class Lab4Task3 {
    public static int findMissingNumber(int[] arr, int n) {
        int totalSum = n * (n + 1) / 2;  // Sum of all numbers from 0 to n
        int arrSum = 0;  // Sum of elements in the array
        for (int num : arr) {
            arrSum += num;
        }
        return totalSum - arrSum;
    }
    public static void main(String[] args) {
        int[] arr = {3, 7, 1, 2, 8, 4, 5};  // Example array
        int n = 8;  // The length of the array is 7, but the numbers are from 0 to 8, so n = 8       
        System.out.println("The missing number is: " + findMissingNumber(arr, n));
    }
}

# Task 4
import java.util.Arrays;
public class Lab4Task4 {
    public static void zigzagSort(int[] arr) {
        boolean flag = true;       
        for (int i = 0; i < arr.length - 1; i++) {
            if (flag) {
                if (arr[i] > arr[i + 1]) {
                    int temp = arr[i];
                    arr[i] = arr[i + 1];
                    arr[i + 1] = temp;
                }
            } else {
                if (arr[i] < arr[i + 1]) {
                    int temp = arr[i];
                    arr[i] = arr[i + 1];
                    arr[i + 1] = temp;
                }
            }
            flag = !flag;
        }
    }
    public static void main(String[] args) {
        int[] arr = {4, 3, 7, 8, 6, 2, 1};
        System.out.println("Original Array: " + Arrays.toString(arr));     
        zigzagSort(arr);        
        System.out.println("Zigzag Sorted Array: " + Arrays.toString(arr));
    }
}















