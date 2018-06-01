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
