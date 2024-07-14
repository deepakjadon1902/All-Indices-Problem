
import java.util.ArrayList;
import java.util.Scanner;
public class Main {
    public static ArrayList<Integer> findAllIndices(int[] arr, int currentIndex, int M, ArrayList<Integer> indices) {
        if (currentIndex == arr.length) {
            return indices;
        }
        if (arr[currentIndex] == M) {
            indices.add(currentIndex);
        }
        return findAllIndices(arr, currentIndex + 1, M, indices);
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[] arr = new int[N];
        for (int i = 0; i < N; i++) {
            arr[i] = scanner.nextInt();
        }
        int M = scanner.nextInt();
        ArrayList<Integer> indices = new ArrayList<>();
        indices = findAllIndices(arr, 0, M, indices);
        for (int index : indices) {
            System.out.print(index + " ");
        }
    }
}
