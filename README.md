# Design-Week1

Question- Minimum String Length After Removing Substrings

#include <iostream>
#include <stack>
#include <string>

int minLength(std::string s) {
    std::stack<char> stack;

    for (char c : s) {
        if (!stack.empty() && 
            ((stack.top() == 'A' && c == 'B') || (stack.top() == 'C' && c == 'D'))) {
            stack.pop(); 
        } else {
            stack.push(c); 
        }
    }

    return stack.size();  
}

int main() {
    std::string s;

    std::cout << "Enter a string: ";
    std::cin >> s;

    int result = minLength(s);

    std::cout << "Minimum possible length of the resulting string: " << result << std::endl;

    return 0;
}



1)Calculate the sum of the digits of a given number.

#include <iostream>

int sumOfDigits(int num) {
    int sum = 0;
    while (num != 0) {
        sum += num % 10;  
        num /= 10;        
    }
    return sum;
}

int main() {
    int number;

    std::cout << "Enter a number: ";
    std::cin >> number;

    int sum = sumOfDigits(number);

   
    std::cout << "Sum of the digits: " << sum << std::endl;

    return 0;
}


2) Determine if a given year is a leap year.

#include <iostream>

bool isLeapYear(int year) {
   
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
        return true;
    } else {
        return false;
    }
}

int main() {
    int year;

    
    std::cout << "Enter a year: ";
    std::cin >> year;

   
    if (isLeapYear(year)) {
        std::cout << year << " is a leap year." << std::endl;
    } else {
        std::cout << year << " is not a leap year." << std::endl;
    }

    return 0;
}


3)Convert temperatures between Celsius and Fahrenheit.       

#include <iostream>

double celsiusToFahrenheit(double celsius) {
    return (celsius * 9.0 / 5.0) + 32;
}

double fahrenheitToCelsius(double fahrenheit) {
    return (fahrenheit - 32) * 5.0 / 9.0;
}

int main() {
    int choice;
    double temperature, convertedTemperature;

    std::cout << "Temperature Conversion Menu:\n";
    std::cout << "1. Convert Celsius to Fahrenheit\n";
    std::cout << "2. Convert Fahrenheit to Celsius\n";
    std::cout << "Enter your choice (1 or 2): ";
    std::cin >> choice;

    if (choice == 1) {
        std::cout << "Enter temperature in Celsius: ";
        std::cin >> temperature;
        convertedTemperature = celsiusToFahrenheit(temperature);
        std::cout << "Temperature in Fahrenheit: " << convertedTemperature << "°F" << std::endl;
    } else if (choice == 2) {
        std::cout << "Enter temperature in Fahrenheit: ";
        std::cin >> temperature;
        convertedTemperature = fahrenheitToCelsius(temperature);
        std::cout << "Temperature in Celsius: " << convertedTemperature << "°C" << std::endl;
    } else {
        std::cout << "Invalid choice!" << std::endl;
    }

    return 0;
}



