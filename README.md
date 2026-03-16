# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```py
#include <stdio.h>
#include <math.h>

int power(int a, int b, int p) {
    int result = 1;
    for(int i = 0; i < b; i++) {
        result = (result * a) % p;
    }
    return result;
}

int main() {
    int p, g, a, b;
    int A, B, keyA, keyB;

    printf("Enter prime number (p): ");
    scanf("%d", &p);

    printf("Enter primitive root (g): ");
    scanf("%d", &g);

    printf("Enter private key for User A: ");
    scanf("%d", &a);

    printf("Enter private key for User B: ");
    scanf("%d", &b);

    A = power(g, a, p);
    B = power(g, b, p);

    printf("Public key of User A = %d\n", A);
    printf("Public key of User B = %d\n", B);

    keyA = power(B, a, p);
    keyB = power(A, b, p);

    printf("Secret key computed by User A = %d\n", keyA);
    printf("Secret key computed by User B = %d\n", keyB);

    return 0;
}
```


## Output:

<img width="463" height="363" alt="image" src="https://github.com/user-attachments/assets/43ca12a5-80b8-4217-bbe5-d0f5bb4a210d" />


## Result:
  The program is executed successfully

