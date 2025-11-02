# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char plaintext[9]; // 8 chars + null terminator
    char key[9];       // 8 chars + null terminator
    char ciphertext[9];
    char decrypted[9];

    // Input plaintext
    printf("Enter 8-character plaintext: ");
    scanf("%[^\n]s", plaintext);

    // Input key
    printf("Enter 8-character key: ");
    scanf("%8s", key);

    // Encrypt (XOR each byte with key)
    for (int i = 0; i < 8; i++) {
        ciphertext[i] = plaintext[i] ^ key[i];
    }
    ciphertext[8] = '\0';

    // Decrypt (XOR again with key)
    for (int i = 0; i < 8; i++) {
        decrypted[i] = ciphertext[i] ^ key[i];
    }
    decrypted[8] = '\0';

    // Print results
    printf("Ciphertext (hex): ");
    for (int i = 0; i < 8; i++) {
        printf("%02X ", (unsigned char)ciphertext[i]);
    }
    printf("\n");

    printf("Decrypted text: %s\n", decrypted);

    return 0;
}

```
## Output:

<img width="374" height="154" alt="image" src="https://github.com/user-attachments/assets/de99011f-090a-4e46-8f97-83ed4cc13254" />

## Result:
  The program is executed successfully

