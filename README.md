#include <iostream>
#include <vector>
#include <string>
#include <cstdlib>   // for rand()
#include <ctime>    // for time
using namespace std;

// Function 1: Decimal to Binary
string decimalToBinary(int decimal) {
    if (decimal == 0) return "0";

    vector<int> binary;
    int num = decimal;
    while (num > 0) {
        binary.push_back(num % 2);
        num /= 2;
    }

    string result = "";
    for (int i = binary.size() - 1; i >= 0; i--) {
        result += to_string(binary[i]);
    }
    return result;
}

// Function 2: Binary to Decimal
int binaryToDecimal(string binary) {
    int decimal = 0;
    for (char bit : binary) {
        decimal = decimal * 2 + (bit - '0');
    }
    return decimal;
}

// Function 3: Decimal to Hexadecimal
string decimalToHexadecimal(int decimal) {
    if (decimal == 0) return "0";
    string hex = "";
    string hexChars = "0123456789ABCDEF";
    while (decimal > 0) {
        hex = hexChars[decimal % 16] + hex;
        decimal /= 16;
    }
    return hex;
}

// Function 4: Hexadecimal to Decimal
int hexadecimalToDecimal(string hex) {
    int decimal = 0;
    for (char digit : hex) {
        if (isdigit(digit)) {
            decimal = decimal * 16 + (digit - '0');
        } else {
            decimal = decimal * 16 + (toupper(digit) - 'A' + 10);
        }
    }
    return decimal;
}

// Function: Demo (random number between 0 and 99 converted to binary)
void demo() {
    srand(time(0)); 
    int randomNumber = rand() % 100;
    cout << "Generated number: " << randomNumber << endl;
    cout << "Binary equivalent: " << decimalToBinary(randomNumber) << endl;
}
