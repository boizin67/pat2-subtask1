# pat2-subtask1

// ============================================================
// PAT 2 - Subtask 2: Morse Code Translator
// This program translates an English message into Morse code.
// It accepts user input, converts lowercase to uppercase,
// ignores numbers and symbols, and displays the Morse code.
// ============================================================

#include <iostream>
#include <string>
#include <cctype>

using namespace std;

int main() {

    // Morse code array for letters A-Z
    string morseCode[26] = {
        ".-", "-...", "-.-.", "-..", ".", "..-.",
        "--.", "....", "..", ".---", "-.-", ".-..",
        "--", "-.", "---", ".--.", "--.-", ".-.",
        "...", "-", "..-", "...-", ".--", "-..-",
        "-.--", "--.."
    };

    string message;
    string fullMorse = "";

    cout << "======================================" << endl;
    cout << "       MORSE CODE TRANSLATOR" << endl;
    cout << "======================================" << endl;

    cout << "Enter a message: ";
    getline(cin, message);

    cout << "\n--- Morse Code for Each Letter ---\n" << endl;

    for (int i = 0; i < message.length(); i++) {

        char currentChar = toupper(message[i]);

        if (currentChar >= 'A' && currentChar <= 'Z') {

            int index = currentChar - 'A';

            cout << currentChar << ": " << morseCode[index] << endl;

            if (fullMorse != "") {
                fullMorse += "   ";
            }

            fullMorse += morseCode[index];
        }
    }

    cout << "\n--- Full Morse Code Message ---" << endl;
    cout << fullMorse << endl;

    cout << "\n======================================" << endl;

    return 0;
}
