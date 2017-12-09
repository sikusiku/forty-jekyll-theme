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
암호화 된 데이터를 볼 수도 있는 의도하지 않은 이로부터 데이터를 숨길 수 있음을 확신하기 위해 암호화를 사용한다.
암호문을 평문으로 되돌리는 과정을 복호화(decryption)라고 한다.
Figure 1-1은 이 과정에 대한 그림이다.
![Figure 1-1. Encryption and Decryption](https://users.ece.cmu.edu/~adrian/630-f04/PGP-intro_files/fig1-1.gif)

## What is Cryptography?
Cryptography는 데이터를 암호화/복호화 하기 위해 수학을 사용하는 과학의 한 분야이다.
Cryptography는 민감한 정보를 저장하거나 인터넷과 같은 안전하지 않은 네트워크를 통해 
의도하지 않은 자는 이해할 수 없도록 전달하는 것을 가능하게 한다.
Cryptography는 데이터를 보호하는 학문인 것에 비해, Cryptanalysis는 이것을 분석하고 안전한 통신을 깨뜨리는 학문이다.
전통적인 Cryptanalysis는 분석적 추론, 수학적 응용 프로그램, 패턴 찾기, 인내심, 결단력 그리고 운과 관련있었다.
Cryptanalysist들을 Attacker라 부르기도 한다.
Cryptonology는 Cryptography와 Cryptanalysis를 모두 포함한다.

## Strong Cryptography
> Cryptography는 이 세상에 두 종류가 존재한다 : 어린 여동생으로부터 당신의 파일을 읽는 것을 멈추게 하거나,
> 거대한 정부가 당신의 파일을 읽는 것을 멈추게 하는 것. 이 책은 후자에 대한 것이다.
> <BR /> --Bruce Schneier, Applied Cryptography: Protocols, Algorithms, and Source Code in C.

