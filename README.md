#include <stdio.h>

// Function prototypes
double add(double a, double b);
double subtract(double a, double b);
double multiply(double a, double b);
double divide(double a, double b);

int main() {
    double num1, num2, result;
    char operator;
    printf("hi!);
    printf("Simple Calculator\n");
    printf("Enter an operation in the format: number1 operator number2\n");
    printf("For example: 5.5 + 3.2\n");

    // User input
    printf("Enter your calculation: ");
    if (scanf("%lf %c %lf", &num1, &operator, &num2) != 3) {
        printf("Invalid input. Please follow the format: number1 operator number2\n");
        return 1;
    }

    // Perform the operation
    switch (operator) {
        case '+':
            result = add(num1, num2);
            break;
        case '-':
            result = subtract(num1, num2);
            break;
        case '*':
            result = multiply(num1, num2);
            break;
        case '/':
            if (num2 == 0) {
                printf("Error: Division by zero is not allowed.\n");
                return 1;
            }
            result = divide(num1, num2);
            break;
        default:
            printf("Invalid operator. Please use one of: +, -, *, /.\n");
            return 1;
    }

    // Display the result
    printf("Result: %.2lf\n", result);
    return 0;
}

// Function definitions
double add(double a, double b) {
    return a + b;
}

double subtract(double a, double b) {
    return a - b;
}

double multiply(double a, double b) {
    return a * b;
}

double divide(double a, double b) {
    return a / b;
}
