#include <iostream>
#include <string>
using namespace std;

// Function to check if a character is a vowel
bool isVowel(char ch) {
    ch = tolower(ch); // Normalize to lowercase
    return ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u';
}

// Function to remove vowels from a string
string removeVowels(const string& input) {
    string result = "";
    for (size_t i = 0; i < input.length(); ++i) {
        if (!isVowel(input[i])) {
            result += input.substr(i, 1); // Add non-vowel character
        }
    }
    return result;
}

int main() {
    string userInput;
    cout << "Enter a string: ";
    getline(cin, userInput);

    string noVowels = removeVowels(userInput);
    cout << "String without vowels: " << noVowels << endl;

    return 0;
}

