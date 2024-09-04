// project_intern
//This is my repo to put my projects of codealpha
import java.util.ArrayList;
import java.util.Scanner;

public class StudentGrades {

    public static void main(String[] args) {
        // Create an ArrayList to store student grades
        ArrayList<Integer> grades = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        
        // Input student grades
        System.out.println("Enter student grades (type -1 to finish):");
        while (true) {
            int grade = scanner.nextInt();
            if (grade == -1) {
                break;
            }
            grades.add(grade);
        }

        // Compute the average, highest, and lowest scores
        if (grades.isEmpty()) {
            System.out.println("No grades entered.");
        } else {
            int total = 0;
            int highest = grades.get(0);
            int lowest = grades.get(0);
            
            for (int grade : grades) {
                total += grade;
                if (grade > highest) {
                    highest = grade;
                }
                if (grade < lowest) {
                    lowest = grade;
                }
            }

            double average = (double) total / grades.size();
            
            // Display results
            System.out.println("Average score: " + average);
            System.out.println("Highest score: " + highest);
            System.out.println("Lowest score: " + lowest);
        }
        
        scanner.close();
    }
}

