# 피쉬 쉘(Fish Shell) 한글화 문서 [비공식]

> *[<b>문서</b>](https://j2doll.github.io/fish-shell-docs-kor/doc/)*

> *[자습서](https://j2doll.github.io/fish-shell-docs-kor/tutorial/)*

> *[디자인](https://j2doll.github.io/fish-shell-docs-kor/design/)*

> *[명령](https://j2doll.github.io/fish-shell-docs-kor/commands/)*

> *[FAQ](https://j2doll.github.io/fish-shell-docs-kor/faq/)*

> *[라이센스](https://j2doll.github.io/fish-shell-docs-kor/license-fish/)*

# 문서

## 소개 (Introduction)

이것은 편리하고 상호 반응하는 피쉬 쉘(Fish Shell)을 위한 문서입다. 피쉬는 사용자 친화적인 명령 줄(Command Line) 쉘입니다. 쉘(Shell)은 다른 프로그램을 실행하는 데 사용되는 프로그램입니다. 피쉬에 대한 최신 정보는 피쉬 쉘 홈페이지를 방문하십시오. [https://fishshell.com](https://fishshell.com)

## 구문 개요 (Syntax overview)

피쉬와 같은 쉘은 명령을 내림으로써 사용됩니다. 모든 피쉬 명령은 동일한 간단한 구문을 따릅니다.
명령은 명령의 이름 뒤에 임의의 인수를 쓰면 실행됩니다.

예:
 echo hello world

echo 명령을 호출합니다. echo는 화면에 인수(argument)를 쓰는 명령(command)입니다. 위의 예에서 출력은 'hello world'가 됩니다. 피쉬의 모든 것은 명령으로 끝납니다. 일련의 명령을 여러 번 수행하는 명령, 변수를 할당하는 명령, 명령 그룹을 단일 명령으로 처리하는 명령 등이 존재합니다. 모든 단일 명령은 동일하고 간단한 구문을 따릅니다.

위에 사용된 echo 명령에 대한 자세한 내용을 보려면 echo 명령의 매뉴얼 페이지를 다음과 같이 입력하십시오:
 man echo

man은 주어진 주제에 매뉴얼(manual) 페이지를 표시하는 명령이다. man 명령은 매뉴얼 페이지의 이름을 인수로 표시합니다. 대부분의 컴퓨터에는 거의 모든 명령에 대한 매뉴얼 페이지가 있습니다. 또한 시스템 라이브러리와 중요한 파일과 같은 많은 다른 것들에 대한 매뉴얼 페이지가 있습니다.

컴퓨터의 모든 프로그램을 피쉬의 명령으로 사용할 수 있습니다. 프로그램 파일이 PATH의 디렉토리 중 하나에 있으면 프로그램 이름을 입력하기만 하면됩니다.

그렇지 않으면, 디렉토리를 포함한 전체 파일 이름을 사용해야 합니다.
 (예를 들어 /home/me/code/checkers/checkers 또는 ../checkers)

다음은 유용한 명령들의 목록입니다.

cd, 현재 디렉토리를 변경하십시오.
ls, 파일 및 디렉토리 나열
man, 화면에 설명서 페이지를 표시하십시오.
mv, 파일 이동 (이름 바꾸기)
cp, 파일 복사
open, 각 파일 유형과 연관된 기본 응용 프로그램으로 파일 열기
less,파일의 내용을 나열하십시오

명령(Command)과 매개변수(Parameter)는 공백 문자 ''로 구분됩니다.

모든 명령은 개행(즉, 리턴 키를 누름) 또는 세미콜론 ';'으로 끝납니다. 하나 이상의 명령을 세미콜론으로 구분하여 동일한 줄에 작성할 수도 있습니다.

스위치(Switch)는 매우 일반적인 특수 유형의 인수입니다.
 
스위치는 거의 항상 하나 이상의 하이픈 '-'로 시작하여 명령이 작동하는 방식을 변경합니다.
 
예를 들어, 'ls' 명령은 대개 현재 작업 디렉토리에있는 모든 파일과 디렉토리를 나열합니다.
 
거기에 '-l' 스위치를 사용하면 'ls' 의 동작이 변경되어 파일 이름 뿐만 아니라 각 파일의 크기, 권한, 소유자 및 수정 시간을 표시할 수 있습니다.

스위치는 명령마다 다르며 각 명령에 대해서는 매뉴얼 페이지에 설명되어 있습니다.

일부 스위치는 대부분의 명령에 공통적으로 사용됩니다.

예를 들어 '--help' 는 일반적으로 도움말 텍스트를 표시하고, '-i' 는 대개 작업을 하기 전에 대화형 프롬프트를 켜고, '-f' 는 꺼지게 합니다.


## 인용 부호 (Quotes)

때로는 매개변수 확장(parameter expansion) 및 문자 이스케이프(character escapes)와 같은 기능이 사용됩니다.

이런 경우 사용자는 '(작은 따옴표) 또는 "(큰 따옴표)로 따옴표 안에 매개 변수를 쓸 수 있습니다. 작은 따옴표로 묶은 문자열과 큰 따옴표로 묶은 문자열 사이에는 중요한 차이점이 하나 있습니다.

큰 따옴표로 묶은 문자열을 사용할 때 변수 확장이 여전히 발생합니다.

그 외에는 다른 종류의 확장(중괄호 확장 및 매개 변수 확장 포함)이 수행되지 않으며 매개 변수에 공백이 포함될 수 있으며, 이스케이프 시퀀스는 무시됩니다.

작은 따옴표 안에 허용되는 유일한 백슬래시 이스케이프(backslash escape)는 작은 따옴표(single quote)를 이스케이프하는 \ ' 이고, 백슬래시(backslash) 심볼을 이스케이프하는 것은 \\ 입니다.

작은 따옴표는 큰 따옴표 안에 특별한 의미가 없으며 그 반대의 경우도 마찬가지입니다.

예:

```sh
rm "cumbersome filename.txt"
```

위 예제는 파일 'cumbersome filename.txt' 를 제거할 것입니다.

반면,

```sh
rm cumbersome filename.txt
```

위 예제는 두 개의 파일 'cumbersome'와 'filename.txt' 를 제거합니다.

<b> //작성중// </b>

빠른 이해를 하시려면 [자습서](https://j2doll.github.io/fish-shell-docs-kor/tutorial/)를 참조하세요.


