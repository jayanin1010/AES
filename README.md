# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:

      #include <stdio.h>
      #include <string.h>
      
      // Function to perform a simple XOR-based AES-like encryption
      void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext) 
      {
          int i;
          int keyLength = strlen(key);
      
          for (i = 0; i < strlen(plaintext); i++) 
          {
              ciphertext[i] = plaintext[i] ^ key[i % keyLength];
          }
          ciphertext[i] = '\0'; 
      }
      
      // Function to decrypt (XOR again with same key)
      void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText) 
      {
          int i;
          int keyLength = strlen(key);
      
          for (i = 0; i < strlen(ciphertext); i++) 
          {
              decryptedText[i] = ciphertext[i] ^ key[i % keyLength];
          }
          decryptedText[i] = '\0'; 
      }
      
      // Function to print ciphertext in ASCII values
      void printASCII(char *ciphertext) 
      {
          printf("Encrypted Message (ASCII values): ");
          for (int i = 0; i < strlen(ciphertext); i++) 
          {
              printf("%d ", (unsigned char)ciphertext[i]);
          }
          printf("\n");
      }
      
      int main() 
      {
          char plaintext[100], key[100], ciphertext[100], decryptedText[100];
      
          printf("\n***** Simulation of AES (XOR-based) Encryption and Decryption *****\n\n");
      
          // Get plaintext
          printf("Enter the plaintext: ");
          scanf("%s", plaintext);
      
          // Get key
          printf("Enter the key: ");
          scanf("%s", key);
      
          // Encrypt
          simpleAESEncrypt(plaintext, key, ciphertext);
          printf("\nOriginal Message: %s\n", plaintext);
          printASCII(ciphertext);
      
          // Decrypt
          simpleAESDecrypt(ciphertext, key, decryptedText);
          printf("Decrypted Message: %s\n", decryptedText);
      
          return 0;
      }

# OUTPUT:
<img width="763" height="340" alt="image" src="https://github.com/user-attachments/assets/cc92544f-297f-495b-98b0-cf57ccd482d4" />



# RESULT:
Thus the expected output is achieved.

