# Cryptography

## Introduction to Cryptography

* **Cryptography** requires two steps: **encryption** and **decryption**. The encryption process uses a cipher in order to encrypt plaintext and turn it into ciphertext. Decryption, on the other hand, applies that same cipher to turn the ciphertext back into plaintext.
​
* **Encryption**: scrambling the data according to a secret key (in this case, the alphabet shift).
* **Decryption** : recovering the original data from scrambled data by using the secret key.
* **Code cracking** : uncovering the original data without knowing the secret, by using a variety of clever techniques.
​
* **Types of Cryptography** :

1. **Hashing**  : Hashing is a type of cryptography that changes a message into an unreadable string of text for the purpose of verifying the message’s contents, not hiding the message itself.
2. **Symmetric Cryptography**:  This type of cryptography uses a single key to encrypt a message and then decrypt that message upon delivery.
3. **Asymmetric Cryptography** :Asymmetric cryptography (as the name suggests) uses two different keys for encryption and decryption, as opposed to the single key used in symmetric cryptography. The first key is a public key used to encrypt a message, and the second is a private key which is used to decrypt them.
4. **Key Exchange Algorithms**
​

* **The 4 Types of Cryptographic Functions** :

1. Authentication
2. Nonrepudiation
3. Confidentiality
4. **Integrity**: The most common way to do accomplish data integrity through cryptography is by using cryptographic hashes to safeguard information with a secure checksum.
​

## Ceasar Cipher

* In cryptography, a **Caesar cipher**, also known as **Caesar's cipher**, the **shift cipher**, **Caesar's code** or **Caesar shift**, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
​
* The Caesar cipher can be easily broken even in a ciphertext-only scenario. Two situations can be considered:
  * an attacker knows (or guesses) that some sort of simple substitution cipher has been used,
​
​
​

# Encruption

 One of the earliest encryption techniques is the Caesar Cipher, invented by Julius Caesar more than two thousand years ago to communicate messages to his allies.
 The Caesar Cipher is a great introduction to encryption, decryption, and code cracking, thanks to its simplicity.

## Encrypting a message

​
Imagine Caesar wants to send this message:
​
    SECRET MEETING AT THE PALACE
​
Here's what that might look like encrypted:
​
    YKIXKZ SKKZOTM GZ ZNK VGRGIK
​
 That looks an awfully lot like gobbledygook at first, but this encrypted message is actually very related to the original text.
 The Caesar Cipher is a simple substitution cipher which replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount.
​

# Decrypting a message

According to historical records, Caesar always used a shift of 3. As long as his message recipient knew the shift amount, it was trivial for them to decode the message.
Imagine Caesar sends this message to a comrade:
​
    EHZDUH EUXWXV
​
They can then decode the message with certainty. The first letter "E" was shifted by 3 from "B", the second letter "H" was shifted by 3 from "E", etc. The result is this ominous message:
​
    BEWARE BRUTUS
​

# Frequency analysis

 Human languages tend to use some letters more than others. For example, "E" is the most popular letter in the English language. We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.
