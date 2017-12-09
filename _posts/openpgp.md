# How PGP works
  (from https://users.ece.cmu.edu/~adrian/630-f04/PGP-intro.html)
  
## The Basics of Cryptography
Julius Caesar가 그의 장군들에게 메시지를 보내었을 때, 그는 그의 메신져를 믿지 못했다. 
그래서 그는 'A'를 'B'로, 'B'를 'E'로 바꾸는 것과 같이 모든 알파벳을 변경 했다.
"Shift by 3"이라는 룰을 아는 사람만이 그의 메시지를 해독할 수 있었다.
우리는 이것에서 시작한다.

## Encryption and Decryption
특별한 수단 없이도 읽을 수 있거나 이해할 수 있는 데이터를 평문(plaintext or cleartext)라 부른다.
이러한 평문의 본질을 감출 수 있는 위장 방법을 암호화(encryption)이라고 부른다.
평문을 암호화 한 결과로 생성되는 읽을 수 없고 알 수 없는 데이터를 암호문(ciphertext)라 한다.
