import java.util.Scanner;

public class WaveDislay {
	// 5 5
	// 1 2 3 4 5
	// 6 7 8 9 10
	// 11 12 13 14 15
	// 16 17 18 19 20
	// 21 22 23 24 25
	// Sample Output 0
	//
	// 1 2 3 4 5 10 9 8 7 6 11 12 13 14 15 20 19 18 17 16 21 22 23 24 25
	// 1 6 11 16 21 22 17 12 7 2 3 8 13 18 23 24 19 14 9 4 5 10 15 20 25
	public static void main(String[] args) {

		Scanner scn = new Scanner(System.in);
		int x = scn.nextInt();
		int y = scn.nextInt();
		int[][] arr = new int[x][y];
		for (int i = 0; i < x; i++) {
			for (int j = 0; j < y; j++) {
				int z = scn.nextInt();
				arr[i][j] = z;
			}
		}
		display(arr);
		System.out.println();
		display2(arr);
	}

	private static void display2(int[][] arr) {
		int rmin = 0;
		int rmax = arr.length - 1;
		int cmin = 0;
		int cmax = arr[0].length - 1;
		int tno = arr.length * arr[0].length - 1;
		int counter = 0;
		while (counter <= tno) {
			if (cmin % 2 == 0) {
				for (int row = rmin; row <= rmax && counter <= tno; row++) {
					counter++;
					System.out.print(arr[row][cmin] + " ");
				}
			}
			cmin++;
			if (cmin % 2 == 1) {
				for (int row = rmax; row >= rmin && counter <= tno; row--) {
					counter++;
					System.out.print(arr[row][cmin] + " ");
				}
			}
			cmin++;
		}

	}

	public static void display(int[][] arr) {
		int rmin = 0;
		int rmax = arr.length - 1;
		int cmin = 0;
		int cmax = arr[0].length - 1;
		int tno = arr.length * arr[0].length - 1;
		int counter = 0;
		while (counter <= tno) {
			if (rmin % 2 == 0) {
				for (int col = cmin; col <= cmax && counter <= tno; col++) {
					counter++;
					System.out.print(arr[rmin][col] + " ");

				}
			}
			rmin++;
			if (rmin % 2 == 1) {
				for (int col = cmax; col >= cmin && counter <= tno; col--) {
					counter++;
					System.out.print(arr[rmin][col] + " ");
				}
			}
			rmin++;
		}

	}

}
