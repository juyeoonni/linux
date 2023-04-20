---
layout: home
---

# 리눅스 파이프

## 파이프

두 개 이상의 프로세스 간 통신을 가능하게하는 기능. 

 ‘`|`’기호로 나타내며, 앞의 명령어의 실행 결과(표준 출력)를 뒤의 명령어의 입력(표준 입력)으로 전달하여 여러 명령어를 연결하여 하나의 명령어처럼 사용

입출력 스트림

![입출력스트림](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F9972043E5AFA5A4C1A)

파이프(‘`|`’)를 통해 이전의 명령어의 결과를 다음 명령어의 입력값으로 사용

![파이프 생성](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F99041C365AFA5A4C11)

### 파이프 특징

- 파이프는 단방향 통신
    - 한 프로세스의 출력을 다른 프로세스의 입력으로 전달하는 단방향 통신 방식
- 메모리 기반 (IPC Inter-Process Communication)
    - 메모리를 사용하여 프로세스간 데이터 전송
- Shell에서 직접 사용 가능
    - Shell에서 제공하는 기능이므로, 명령어를 조합하여 사용 가능

### 파이프의 장점

- 복잡한 명령어를 간단하게 만들 수 있음
    - 명령을 연결함으로써 파이프를 통해 동시에 작동하고 개별 기능을 배가할 수 있다
- 명령들 사이에 지속적인 데이터 전송을 가능하게 하여 임시 텍스트 파일이나 디스플레이 화면을 통해 정보를 전달할 필요가 없음
- 재사용성이 높다
    - 파이프로 연결한 명령어들은 조합을 바꾸거나 순서를 바꿔 재사용 가능
- 유연성이 높다
    - 명령어를 조합하면, 각 명령어의 출력 결과를 중간에 확인할 수 있어서, 중간 단계의 결과를 바탕으로 새로운 명령어를 추가하거나 조합을 변경할 수 있음

### 파이프 명령어

- grep - 패턴과 일치하는 라인 출력
    - `ls -l | grep ".txt"` 
    현재 디렉토리에서 txt확장자를 가진 파일 검색
- sort - 데이터 정렬
    - `cat file.txt | sort` 
    파일 내용을 알파벳 순으로 정렬
- head - 파일의 처음 일부분 출력
    - `ls -l head -n 5` 
    현재 디렉토리에서 상위 5개 파일 출력
- tail - 파일의 마지막 일부분 출력
    - `ls -l | tail -n 3` 
    현재 디렉토리에서 하위 3개 파일 출력
- cut - 텍스트 파일에서 원하는 부분만 추출
    - `cat file.txt | cut -d "," -f 2
    ','` 구분자로 구분된 파일에서 두 번째 필드만 추출
- awk - 텍스트 파일을 가공하여 출력
    - `cat file.txt | awk '{print $2, $1}'`
    파일에서 두 번째 필드와 첫 번째 필드를 순서대로 출력