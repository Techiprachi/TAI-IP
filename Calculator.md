import java.util.Scanner;
import java.lang.Math;

public class AdvancedCalculator {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        while (true) {
            System.out.println("Options:");
            System.out.println("Enter 'add' for addition");
            System.out.println("Enter 'subtract' for subtraction");
            System.out.println("Enter 'multiply' for multiplication");
            System.out.println("Enter 'divide' for division");
            System.out.println("Enter 'sin' for sine function");
            System.out.println("Enter 'cos' for cosine function");
            System.out.println("Enter 'tan' for tangent function");
            System.out.println("Enter 'sqrt' for square root");
            System.out.println("Enter 'exp' for exponentiation");
            System.out.println("Enter 'quit' to end the program");
            
            System.out.print(": ");
            String userChoice = input.nextLine();
            
            if (userChoice.equals("quit")) {
                break;
            } else if (userChoice.equals("add") || userChoice.equals("subtract") || userChoice.equals("multiply") || userChoice.equals("divide")) {
                System.out.print("Enter first number: ");
                double num1 = input.nextDouble();
                System.out.print("Enter second number: ");
                double num2 = input.nextDouble();
                
                if (userChoice.equals("add")) {
                    System.out.println("Result: " + (num1 + num2));
                } else if (userChoice.equals("subtract")) {
                    System.out.println("Result: " + (num1 - num2));
                } else if (userChoice.equals("multiply")) {
                    System.out.println("Result: " + (num1 * num2));
                } else if (userChoice.equals("divide")) {
                    if (num2 == 0) {
                        System.out.println("Division by zero is not allowed");
                    } else {
                        System.out.println("Result: " + (num1 / num2));
                    }
                }
            } else if (userChoice.equals("sin") || userChoice.equals("cos") || userChoice.equals("tan")) {
                System.out.print("Enter the angle in degrees: ");
                double angle = input.nextDouble();
                double angleRad = Math.toRadians(angle);
                
                if (userChoice.equals("sin")) {
                    System.out.println("Result: " + Math.sin(angleRad));
                } else if (userChoice.equals("cos")) {
                    System.out.println("Result: " + Math.cos(angleRad));
                } else if (userChoice.equals("tan")) {
                    System.out.println("Result: " + Math.tan(angleRad));
                }
            } else if (userChoice.equals("sqrt")) {
                System.out.print("Enter a number: ");
                double num = input.nextDouble();
                if (num >= 0) {
                    System.out.println("Result: " + Math.sqrt(num));
                } else {
                    System.out.println("Invalid input. Please enter a non-negative number for square root.");
                }
            } else if (userChoice.equals("exp")) {
                System.out.print("Enter the base: ");
                double base = input.nextDouble();
                System.out.print("Enter the exponent: ");
                double exponent = input.nextDouble();
                System.out.println("Result: " + Math.pow(base, exponent));
            } else {
                System.out.println("Invalid input. Please try again.");
            }
            
            // Consume the newline character left in the input buffer
            input.nextLine();
        }
        
        input.close();
    }
}
