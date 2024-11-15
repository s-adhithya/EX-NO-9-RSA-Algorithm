# EX-NO-9-RSA-Algorithm

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:
```
#include <stdio.h>
 #include <math.h>
 // Function to compute GCD
 int gcd(int a, int h) {
    int temp;
    while(1) {
        temp = a % h;
        if (temp == 0)
            return h;
        a = h;
        h = temp;
    }
 }
 int main() {
    printf("Adhithya - 212222240003\n");
    // Two prime numbers
    int p = 3;
    int q = 7;
    
    // Public and private keys
    int n = p * q;
    int phi = (p - 1) * (q - 1);
    int e = 2;
    // Find e such that gcd(e, phi) = 1
    while (e < phi) {
        if (gcd(e, phi) == 1)
            break;
        else
            e++;
    }
    // Choose k (integer multiplier)
    int k = 2;
    
    // Calculate d (Private key)
    int d = (1 + (k * phi)) / e;
    // Message to be encrypted
    int msg = 24;
     printf("Message data = %d\n", msg);
 // Encryption: c = (msg ^ e) % n
 long long c = (long long)pow(msg, e) % n;
 printf("Encrypted data = %lld\n", c);
 // Decryption: m = (c ^ d) % n
 long long m = (long long)pow(c, d) % n;
 printf("Original Message Sent = %lld\n", m);
 return 0;
 }
```


## Output:
![Screenshot 2024-11-15 120300](https://github.com/user-attachments/assets/af9f2c8f-1a71-40d1-beba-c974c21cdd2e)



## Result:
 The program is executed successfully.
