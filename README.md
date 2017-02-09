# ArrayList
1.      Напишете програма, която прочита от конзолата поредица от цели положителни числа.  Поредицата спира когато се въведе празен ред. Програмата трябва да изчислява сумата и  средното аритметично на поредицата.

import java.util.ArrayList;
import java.util.Scanner;

public class Zad {

	static ArrayList<Integer> al = new ArrayList<Integer>();
	
	public  static void main(String[] args) {
		
		al = list();
		
		float sum = 0;
		for(int i = 0; i < al.size(); i++) {
			sum = sum + al.get(i);
		}

		float average = sum/al.size();
		
		System.out.printf("Sum = %.0f%n", sum);
		System.out.println("Average = " + average);
	}

	@SuppressWarnings("resource")
	private static ArrayList<Integer> list() {

	Scanner scan = new Scanner(System.in);
	String line = scan.nextLine();
	if (line.equals(" ")) {
	    scan.close();
	}
	else {
		al.add(Integer.parseInt(line));
		return list();
	}
	
    return al ;
	}
}
