# 6장. 편리한 편집 기술

#### 6장에서 살펴볼 기능

|살펴볼 기능      |명령어 |
|:----------------|:------|
|단어 단위 이동   |w, e, e|
|오퍼레이션 이동<br/>(삭제 명령)|d{motion}|
|약어 매크로      |:ab, :ia, :ca|
|레지스터 목록 확인하기 |:reg|
|레지스터 붙이기  |"{reg}p|
|입력 모드에서<br/>레지스터 붙이기 |(CTRL-R){reg}|

"
## 6.1 단어와 문장 사이를 이동하기

#### 단어나 특별한 경계로 움직이는 키들

|명령어  |설명|
|:-------|:---|
|0       |0번째 열|
|^       |공백을 제외한 행의 시작 부분|
|$       |마지막 열(행의 끝)|
|w       |단어의 시작 위치 혹은 문장부호의 경계를 따라서 이동합니다.<br/>(words forward)|
|e       |w와 같으나, 단어의 끝 부분에 위치합니다.(end of word)|
|b       |w와 비슷하나 진행 방향이 역방향입니다. (words backward)|
|W,E,B   |w, e, b와 비슷하지만 단어가 가진 의미를 따져서 이동합니다. 예를 들어 '/usr/local/bin'이라는 문자열을 만났을 때 w, e, b는 슬래시(/)나 바로 뒤에 있는 문자를 문장부호로 인식하지만, W, E, B는 경로 전체를 단어로 인식합니다.|

#### 괄호, 문단, 블록 단위 이동

|명령어 |설명 |
|:------|:----|
|%      |가장 가까운 괄호 짝으로 이동|
|(, )   |문장 단위의 시작 위치, 끝 위치로 이동|
|{, }   |문단 단위의 시작 위치, 끝 위치로 이동|
|[[, ]] |블록 단위의 시작 위치, 끝 위치로 이동|


<br/>
## 6.2 오퍼레이션 펜딩 모드

#### 삭제 명령어의 다양한 실행 모드

|명령어 |설명 |
|:------|:----|
|d$     |현재 커서 위치부터 행 끝까지 삭제합니다.|
|dd     |현재 행을 삭제합니다.|
|dj     |현재 행과 아래 행을 삭제합니다.|
|dk     |현재 행과 위의 행을 삭제합니다.|
|dw     |현재 켜서 위치부터 단어 끝까지 삭제 합니다.|
|de     |(커서 위치와 상관없이 단어 하나를 지우려면 diw나 daw를 사용합니다.)|
|d^     |현재 커서 위치부터 행 시작 부분까지 삭제합니다.|
|d}     |현재 커서 위치부터 문단 끝까지를 삭제합니다.|

#### {motion}을 사용하는 명령의 예

|명령어    |설명 |
|:---------|:----|
|y{motion} |{motion}만큼 복사|
|d{motion} |{motion}만큼 삭제|
|c{motion} |{motion}만큼 변경(삭제 후 입력 모드로 전환)|


