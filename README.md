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
