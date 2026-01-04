# Fihe1

#include <stdio.h>
#include <string.h>

int main() {
    int choice;
    int shift;
    char message[101];
    char result[101];

 printf("Choose operation:\n");
    printf("1. Encode\n");
    printf("2. Decode\n");
    printf("Enter choice: ");
    scanf("%d", &choice);

 getchar(); // clear buffer

printf("\nEnter your message: ");
fgets(message, 100, stdin);

  printf("Enter shift key (1-25): ");
scanf("%d", &shift);

// If decoding, reverse the shift
if (choice == 2) {
        shift = -shift;
    }
for (int i = 0; message[i] != '\0'; i++) {
char c = message[i];
 // Uppercase letters
        if (c >= 'A' && c <= 'Z') {
 result[i] = (char)((c - 'A' + shift + 26) % 26 + 'A');
        }
 // Lowercase letters
        else if (c >= 'a' && c <= 'z') {
result[i] = (char)((c - 'a' + shift + 26) % 26 + 'a');
        }
// Other characters stay the same
 else {
            result[i] = c;
        }
    }

printf("\n============================\n");
 printf("Original Message: %s", message);
 printf("Shift Key: %d\n",shift < 0 ? -shift : shift);

  if (choice == 1)
printf("Encoded Message: %s", result);
    else
 printf("Decoded Message:
        %s", result);

printf("============================\n");

 return 0;
}
