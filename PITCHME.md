## Cryptopals Set 1 & 2
Adam Block
+++
### Challenge 1
Base 64 Encoding
- Straightforward
- Manually?
+++
### Challenge 2
Fixed XOR
- Straightforward
- Convert hex to int
- Bitwise XOR, then back to hex
+++
### Challenge 3
Single-byte XOR Cipher
- Statistical variance on letter frequency
- Lowest score is the sentence returned
- Result: ANSWER HERE
+++
### Challenge 4
Detect single-character XOR
- Slight variation of Challenge 3
- Preform C3 on all lines
- Lowest score is the sentence returned
- Result: ANSWER HERE
+++
### Challenge 5
Implement repeating-key XOR
- Create a repeating key
- XOR it, simple
+++
### Challenge 6
Break repeating-key XOR
- Find keysize through hamming distance scores on blocks of size n
- Sort characters into their respective locations
- Run the statistical variance test from C3
- Result: ANSWER HERE
+++
### Challenge 7
AES in ECB mode
- Straightforward
- Used pyCrypto
+++
### Challenge 8
Detect AES in ECB mode
- AES ECB is stateless
- Look for identical encrypted blocks
- Result: ANSWER HERE
+++
### Challenge 9
Implement PKCS#7 padding
- Straightforward
- 0x01 for a single byte, 0x2 for two etc.
+++
### Challenge 10
Implement CBC mode
- Used XOR function to combine blocks
- Ciphertext(n-1) XOR Plaintext(n)
- Throw in ECB mode to get CBC block
+++
### Challenge 11
An ECB/CBC detection oracle
- Similar to C8
- If no matches found -> CBC
- If match found -> ECB
- Need string of sufficient size (potential redesign)
+++
### Challenge 12
Byte-at-a-time ECB decryption
- Appended string decryption in ECB
- Fill block with (n-1) single characters ("A")
- Search through ASCII chars to find the character that matches the ECB Block
- When match is found, use n-2 single characts ("A") and found char to find next
- Etc.
+++
### Challenge 13
ECB cut-and-paste
- Form email={INPUT}&uid=10&role=user
- Find admin block with PKCS7 padding by padding input
- Create a input string that will push the "user" into its own block
- Replace that block with the admin block
- Admin obtained
+++
### Challenge 14
Byte-at-a-time ECB decryption Electric Boogaloo
- Random bytes of random size prepended
- Same as C12 in most ways
- Need to isolate prepended data first (padding & blocksize)
- Once isolated, process the same as C12
+++
### Challenge 15
PKCS#7 padding validation
- Ensuring data is padded before unpadding
- Check length
- Check bytes (all should match)
- Ensure the pad is less than the blocksize
+++
### Challenge 16
CBC bitflipping attacks
- Useful attack: Modify data you know the form of
- Scrambles blocks prepended, but non-issue with IV block
- Changed 9admin9true to ;admin=true by changing two bits
