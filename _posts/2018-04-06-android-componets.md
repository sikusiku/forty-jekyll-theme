# Android Framework
## Android architecture
![Android Framework](http://3.bp.blogspot.com/_wK8UgW3iEtU/TGPkS44q8LI/AAAAAAAADgc/x6EBEn2sl3c/s1600/Android+Architecture+-+1.png)
### Applications
* Pre-load App. 이나 일반 App. 이나 동일하게 안드로이드 어플리케이션 스택에 위치.
* Pro-load App. 의 경우 system 권한을 가지거나 LMK에 의해 종료 될 때 영향을 주는 process priority를 임의 설정 가능.
### Application Framework
* Android OS 위에서 기반이 되는 구조.
* 앱은 직접 자신의 생명 주기를 관리하지 않으며 Application Framework에서 이러한 일들을 관장함.
* 엡은 Application Framework 에서 정한 규칙에 따라 작성 되면 됨.
* Native C/C++
  * H/W 제어가 필요하거나 빠른 실행 속도를 요구 하는 경우
  * JNI를 통해 native C/C++ 코드를 사용.
* Thin client / Server 구조
  * 각 manager는 클라이언트인 ###_manager와 server인 ###ManagerService를 포괄하는 개념임.
  * Server 기능은 별도 프로세스인 system_server에서 실행 됨.
  * 앱 프로세스는 컴포넌트의 실행이라는 최소 역할만 수행하고 나머지는 모두 system_server에 위임.
  * system_server는 여러 앱을 통합 관리하는 '통합 문의 채널'.
  * Activity를 포함한 모든 안드로이드 컴포넌트는 system_server를 통해서 관리되고 system_server에서 다시 앱으로 메시지를 보내는 방식으로 동작한다.
