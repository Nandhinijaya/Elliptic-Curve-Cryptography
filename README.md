# Ex-11-Elliptic-Curve-Cryptography-ECC

## Aim:
To implement Elliptic Curve Cryptography (ECC) for encryption
and decryption of the plain text

## Algorithm Steps:

1. Define a mod_exp function for modular exponentiation.
2. Define encrypt_message and decrypt_message functions,
using mod_exp with a public and private key.
3. Set parameters: a small modulus, public key, private key, and
a numeric message representation.
4. Display the plaintext.
5. Encrypt the message using the public key.
6. Print the encrypted result.
7. Decrypt the message using the private key.
8. Print the decrypted result.

## Program:
```
#include <stdio.h>
#include <string.h>

int mod_exp(int base, int exp, int mod) {
    int result = 1;
    for (int i = 0; i < exp; i++) {
        result = (result * base) % mod;
    }
    return result;
}

int encrypt_message(int message, int pub_key, int mod) {
    return mod_exp(message, pub_key, mod);
}

int decrypt_message(int cipher, int priv_key, int mod) {
    return mod_exp(cipher, priv_key, mod);
}

int main() {
    printf("Experiment 11 - Elliptic Curve Cryptography\n");
    
    char plaintext[] = "Nandhini";
    int mod = 17;
    int pub_key = 5;
    int priv_key = 3;
    int message = 7;

    printf("Plaintext message: %s (numeric representation: %d)\n", plaintext, message);

    int encrypted = encrypt_message(message, pub_key, mod);
    printf("Encrypted message: %d\n", encrypted);

    int decrypted = decrypt_message(encrypted, priv_key, mod);
    printf("Decrypted message (numeric): %d\n", decrypted);

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/9bf95f06-2460-4db8-bd06-891cc21141c6)

## Result:
The shared secret is successfully generated using Elliptic Curve
Cryptography.
