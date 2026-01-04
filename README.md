# Fihe1

#include <iostream>
#include <string>
using namespace std;

int main() {
    int choice;
    int shift;
    string message;

   cout << "Choose operation:\n";
    cout << "1. Encode\n";
    cout << "2. Decode\n";
    cout << "Enter choice: ";
    cin >> choice;

   cin.ignore(); // clear buffer

   cout << "\nEnter your message: ";
    getline(cin, message);

  cout << "Enter shift key (1-25): ";
    cin >> shift;

  // For decoding, we reverse the shift
    if (choice == 2) {
        shift = -shift;
    }

   string result = message;

   for (int i = 0; i < message.length(); i++) {
        char c = message[i];

   // Uppercase letters
        if (c >= 'A' && c <= 'Z') {
           result[i] = char((c - 'A' + shift + 26) % 26 + 'A');
        }
        // Lowercase letters
        else if (c >= 'a' && c <= 'z') {
            result[i] = char((c - 'a' + shift + 26) % 26 + 'a');
        }
        // Other characters remain unchanged
        else {
            result[i] = c;
        }
    }

  cout << "\n============================\n";
    cout << "Original Message: " << message << endl;
    cout << "Shift Key: " << abs(shift) << endl;

   if (choice == 1)
        cout << "Encoded Message: " << result << endl;
    else
        cout << "Decoded Message: " << result << endl;

   cout << "============================\n";

   return 0;
}
