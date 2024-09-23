[english_random.txt](https://drive.google.com/file/d/1yuTIqZvHZEcDjSnG3hdMAVeJh28taL0w/view?usp=sharing)

### **The Enigma of Cipherland**

In the mystical land of Cipherland, where cryptography reigns supreme, an ancient cryptographer named Sir Cipherus has hidden his most treasured secrets behind intricate codes. As an aspiring cryptographer, you’ve been chosen to unravel these secrets through a series of cryptographic challenges. Prepare yourself for a journey filled with intrigue and discovery.

---

**Chapter 1: The Substitution Cipher of the Lost Kingdom**

Deep within the Lost Kingdom of Cipherland, Sir Cipherus's final encrypted message has been discovered in an old parchment. This message was protected using a substitution cipher, where each letter of the alphabet is replaced by another letter according to a fixed rule.

1. **The Hidden Message**: The message has been recorded in a file named `english_random.txt`, stripped of all characters except lowercase letters. Your first task is to decode this message.

   **Your Mission:**
   
   - **Count the Letters**: Analyze the frequency of each letter in the file. This will give you clues about the most common letters and help you understand the cipher.
   - **Encrypt the Text**: Using the provided substitution dictionary, encrypt the original stripped message. The dictionary maps letters, such as `a` to `n`, `b` to `o`, and so forth.
   - **Decrypt and Verify**: Decrypt the encrypted text with the same dictionary and ensure it matches the original stripped message.

   **Code Instructions:**

   ```python
   # Step 1: Count letter frequencies
   distribution = letter_distribution("english_random.txt")
   print(distribution)
   
   # Step 2: Encrypt the message
   encrypted_content = substitution_encrypt("english_random.txt", substitution_dict)
   print(encrypted_content)
   
   # Step 3: Decrypt and verify
   decrypted_content = substitution_decrypt("encrypted.txt", substitution_dict)
   if decrypted_content == textstrip("english_random.txt"):
       print("Substitution cipher successfully decrypted!")
   ```

   **Challenge**: Compare the dictionary used for encryption and decryption with the one predicted from frequency analysis. Can you confirm the accuracy of your work?

---

**Chapter 2: The Enigma of the Vigenere Cipher**

As you delve deeper into Cipherland, you encounter Sir Cipherus’s most complex cipher: the Vigenere cipher. This cipher uses a keyword to encrypt and decrypt messages, adding a layer of complexity to the challenge.

1. **The Vigenere Cipher**: The encrypted message is hidden in a file named `encrypted_vignere.txt`, and you need to use the keyword "moon" to decode it.

   **Your Mission:**
   
   - **Encrypt Using Vigenere**: Encrypt the original stripped message with the Vigenere cipher using the keyword "moon".
   - **Decrypt and Confirm**: Decrypt the Vigenere-encrypted message and check if it matches the content in `encrypted_vignere.txt`.
   - **Discover the Keyword**: Use frequency analysis and rotation comparison to find the keyword length and the keyword itself. This involves determining the length of the keyword and then deriving the keyword from the encrypted text.

   **Code Instructions:**

   ```python
   # Encrypt with Vigenere cipher
   vigenere_encrypt("english_random.txt", "moon")
   
   # Decrypt with Vigenere cipher
   vigenere_decrypt("encrypted_vignere.txt", "moon")
   
   # Analyze and find keyword
   print(rotate_compare("encrypted_vignere.txt", 4))
   print(cryptanalyse_vigenere_afterlength("encrypted_vignere.txt", 4))
   print(cryptanalyse_vigenere_findlength("encrypted_vignere.txt"))
   
   # Finalize the keyword and decrypt
   print(cryptanalyse_vigenere("encrypted_vignere.txt"))
   ```

   **Challenge**: Successfully decrypt the Vigenere message and identify the keyword. Ensure your findings are accurate and the decrypted message is correct.

---

**The Grand Triumph**

With the secrets of both the substitution and Vigenere ciphers revealed, you have proven your skill and knowledge. The kingdom of Cipherland celebrates your achievement and the wisdom you have gained. You now hold the key to the cryptographic arts, ready to face any challenge that lies ahead.

---
