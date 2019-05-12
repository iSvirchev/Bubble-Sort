import java.util.Arrays;
import java.util.Scanner;

public class App {

	public static void sort(int[] array) {
		for (int i = array.length; i >= 0; i--) {
			for (int j = 0; j < array.length - 1; j++) {
				if (array[j] > array[j + 1]) {
					swapNumbers(j, j + 1, array);
				}
			}
			printNumbers(array);
		}
	}

	public static void swapNumbers(int i, int j, int array[]) {
		int temp = array[i];
		array[i] = array[j];
		array[j] = temp;
	}

	public static void printNumbers(int array[]) {
		for (int i = 0; i < array.length; i++) {
			System.out.print(array[i] + "; ");
		}
		System.out.println();
	}

	public static void main(String[] args) {
		int[] unsorted = { 15, -5, 12, 32, -17, 9, 4, -34 };
		sort(unsorted);
		
		Scanner scanner = new Scanner(System.in);
		
		int[] input = Arrays
                .stream(scanner.nextLine().split("\\s+")) // separated by spaces
                .mapToInt(Integer::parseInt)
                .toArray();
		
		sort(input);
		
	}
}
