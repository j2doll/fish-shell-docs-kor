# 피쉬 쉘(Fish Shell) 한글화 문서 [비공식]

> *[문서](https://j2doll.github.io/fish-shell-docs-kor/doc/)*

> *[자습서](https://j2doll.github.io/fish-shell-docs-kor/tutorial/)*

> *[디자인](https://j2doll.github.io/fish-shell-docs-kor/design/)*

> *[명령](https://j2doll.github.io/fish-shell-docs-kor/commands/)*

> *[FAQ](https://j2doll.github.io/fish-shell-docs-kor/faq/)*

> *[라이선스](https://j2doll.github.io/fish-shell-docs-kor/license-fish/)*

## 피쉬 쉘 (Fish Shell) 자습서 한글 번역

### 왜 피쉬(fish)인가?
> [Fish:피쉬 또는 Fish Shell:피쉬 쉘 로 발음합니다. 원하실 경우 ‘물고기’로 불러도 됩니다]

- 피쉬(fish)는 스마트하고 사용하기 쉬운 완벽히 준비된 명령행 쉘(Shell)입니다.
	- 잘 알려진 쉘에는 bash 또는 zsh 등이 있습니다. 
- 피쉬(fish)는 구문 강조, 자동 제안 및 탭 완성과 같은 강력한 기능을 지원하며, 사용하기 위하여 장시간 학습하거나 구성할 필요가 없습니다.
- 복잡한 명령과 구성 옵션을 배우지 않고도, 명령줄(command line)을 보다 생산적으로 더 유용하고 재미있게 만들고 싶다면, 피쉬(fish)는 당신이 찾고 있는 것일 수도 있습니다.

### 피쉬 배우기 (Learning fish)
- 이 자습서(튜토리얼)는 커맨드 라인 셸(Command Line Shell)과 유닉스 명령(Unix Command)에 대한 기본적인 지식을 당신이 가지고 있다고 가정합니다.
- 다른 쉘(Shell)에 대해 잘 알고 있으며, 피쉬(fish)가 그들과 다르게 작동되는 것을 알고 싶다면, 타 쉘들과는 다른 마법의 구절을 찾으십시오. 이 쉘은 중요한 차이점을 호출하는데(call out) 사용됩니다.
- 피쉬(fish)를 시작하면 다음과 같이 표시됩니다.

```fish
Welcome to fish, the friendly interactive shell
Type help for instructions on how to use fish
you@hostname ~>
```

- 피쉬(fish)는 사용자 이름, 호스트 이름 및 작업 디렉토리를 보여주는 기본 프롬프트(default prompt)와 함께 제공됩니다. 또한 다음 경로에 프롬프트를 변경하는 방법을 기술하고 있습니다. [https://fishshell.com/docs/current/tutorial.html#tut_prompt](https://fishshell.com/docs/current/tutorial.html#tut_prompt)
- 이제부터는 설명하는 공간을 절약하기 위해 프롬프트는 '>' 인 것으로 가정하여 설명하겠습니다.

### 명령 실행 (Running Commands)

- 피쉬(fish)는 다른 쉘과 같은 명령(command)을 실행합니다.
- 명령을 입력하고 인수를 입력하면 됩니다. 백은 구분 기호입니다.

```fish
> echo hello world
hello world
```

- 역 슬래시(\)가 있는 인수에 리터럴(literal) 공백을 포함하거나 작은 따옴표(') 나 큰 따옴표(“)를 사용할 수 있습니다.

```fish
> mkdir My\ Files
> cp ~/Some\ File 'My Files'
> ls "My Files"
Some File
```

- 명령은 세미콜론(;)으로 연결될 수 있습니다.

### 도움 받기 (Getting Help)

- 피쉬(fish)는 훌륭한 도움말과 맨(man) 페이지를 가지고 있습니다.


 