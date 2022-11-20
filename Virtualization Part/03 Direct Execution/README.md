# Virtualization 
## 03 Direct Execution

---
## Q&A
### fork()는 단순히 프로세스를 복사하는 것이고, exec()는 프로세스를 실행 하기 위해 로딩을 하는 것이다. 그런데 왜 둘을 굳이 분리해서 만들었을까❓
Linux나 Unix는 커맨드를 처리하기 위한 shell이 있다. shell에서 벌어지는 일은 프롬프트($)를 출력해주면, 사용자가 커맨드를 입력하고 엔터를 쳐서 실행하게 되어있다. 이런 과정이 있다보니까, 주어진 명령어를 위한 실행 환경을 만들기 위한 fork(), 주어진 명령을 실행하도록 하는 exec()로 나뉘게 되었다.


### 운영체제의 입장에서는 자원 관리의 책임을 갖고 있기에 제어 문제가 중요하다. 그 이유는 무엇일까?
제어권을 상실하면, 한 프로세서가 영원히 실행을 계속할 수 있고, 컴퓨터를 장악하거나 접근해서는 안되는 정보에 접근할 수 있기 때문이다.


### 프로세서가 System call을 호출하면, trap이 해당 부분의 운영체제 코드를 호출해야 한다. 그러나 호출한 프로세서는 분기할 주소를 명시할 수 없다. 그 이유는 무엇일까?
주소를 명시한다는 것은 커널 내부의 원하는 지점을 접근할 수 있다는 것이기에 위험하기 때문이다. 커널이 임의의 코드를 실행하기 위해서는 접근 권한 검사가 끝난 후 분기해야 한다.