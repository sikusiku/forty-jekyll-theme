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
* System Service 접근
  * 여러 Manager 서버는 시스템 서비스 형태로 존재.
  * 앱에서 접근할 때는 Context의 getSystemService(String name) 메서드를 이용.
  * system_server라는 별도 프로세스에서 실행 되므로 앱에서는 시스템 서비스 접근 시 Binder IPC를 이용한 프로세스 간 통신이 필요.
### Android Runtime
* Dalvik VM은 자바/C/C++로 작성 되어 잇으며 L-OS 부터는 ART로 대체.
* 레지스터 기반의 VM으로 JAVA VM보다 명령이 단순하고 속도가 빠름.
* Core Libraries
  * /system/core 에 위치.
  * 커널을 래핑하거나 추가 기능을 제공하는 역할
  * Library
    * 주로 Native library를 말하며 세 가지 범주로 구분.
    * Bionic : Android custom C library. (libc)
    * Webkit/SQLite/OpenGL 같은 기능 라이브러리
    * Native System Service인 Surface Manager(/system/bin/surfaceflinger), Media Framework(/system/bin/mediaserver)
  * Linux Kernel : Android의 Kernel은 리눅스 Kernel을 기반으로 불필요한 것을 제거하고 기능을 확장(Binder, Ashmene, LMK 등)한 것.
  * Binder IPC.
    * Process 간 통신에 사용.
    * Binder IPC : Binder IPC의 하부 매커니즘
    * Binder RPC : Binder IPC의 용도(remote call)
    * Android component 중 Service와 Content Provider는 Binder를 통해 다른 프로세스에 접근 가능.
  * Binder Thread
    * App. 프로세스에는 Binder Thread 라는 native thread pool이 있고 최대 16개 까지 생성 가능.
    * 다른 프로세스에서 Binder를 통해 접근할 때 이 thread pool을 통해 접근.
## Android source tree
* frameworks : Android framework. android. 으로 시작하는 자바 패키지 포함.
* libcore : 자바 코어 패키지 포함.
* system : Android Init process.
* packages : Android 기본 App.
* bionic : Android standard C library.
* dalvik : Dalvik VM.
* cts : Android Compatibility Test Suits.
* build : Android Build System.
