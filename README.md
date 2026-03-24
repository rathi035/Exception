# Exception
class InvalidAgeException extends Exception {
    InvalidAgeException(String message) {
        super(message);
    }
}

import java.util.Scanner;

public class AgeValidation {

    static void checkAge(int age) throws InvalidAgeException {
        if (age < 0 || age > 100) {
            throw new InvalidAgeException("Age must be between 0 and 100");
        } else {
            System.out.println("Valid Age: " + age);
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter age: ");
            int age = sc.nextInt();

            checkAge(age);

        } catch (InvalidAgeException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}
