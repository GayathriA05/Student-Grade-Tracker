Student Grade Tracker
This Java program allows teachers to input student grades for multiple subjects and provides an analysis of their performance. It calculates and displays the total marks, average percentage, highest score, lowest score, and assigns a grade based on the average percentage.

Features
Input the number of subjects and marks for each subject.
Compute the total marks, average percentage, highest score, and lowest score.
Assign a grade based on the average percentage.
How to Use
Compile the Program: Use javac StudentGradeTracker.java to compile the code.
Run the Program: Execute the compiled code using java StudentGradeTracker.
Input Data:
Enter the number of subjects.
Provide the marks obtained in each subject when prompted.
Code Overview
java
Copy code
import java.util.Scanner;
import java.util.ArrayList;
import java.util.Collections;

public class StudentGradeTracker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Hello, Enter the Number of Subjects: ");
        int numSubjects = scanner.nextInt();

        ArrayList<Integer> marks = new ArrayList<>();
        int totalMarks = 0;

        for (int i = 0; i < numSubjects; i++) {
            System.out.print("Enter marks obtained in Subject " + (i + 1) + ": ");
            int mark = scanner.nextInt();
            marks.add(mark);
            totalMarks += mark;
        }

        double averagePercentage = (double) totalMarks / numSubjects;
        int highestScore = Collections.max(marks);
        int lowestScore = Collections.min(marks);

        System.out.println("\nYour Result is Here:");
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Percentage: " + averagePercentage + "%");
        System.out.println("Highest Score: " + highestScore);
        System.out.println("Lowest Score: " + lowestScore);

        String grade = calculateGrade(averagePercentage);
        System.out.println("Grade: " + grade);

        scanner.close();
    }

    public static String calculateGrade(double percentage) {
        if (percentage >= 90) {
            return "A+";
        } else if (percentage >= 80) {
            return "A";
        } else if (percentage >= 70) {
            return "B";
        } else if (percentage >= 60) {
            return "C";
        } else if (percentage >= 50) {
            return "D";
        } else {
            return "F";
        }
    }
}
Contribution
Feel free to fork the repository, make improvements, or open issues with any bugs or suggestions
