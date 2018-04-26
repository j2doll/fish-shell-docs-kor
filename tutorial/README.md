# 피쉬 쉘(Fish Shell) 한글화 문서 [비공식]

> *[문서](https://j2doll.github.io/fish-shell-docs-kor/doc/)*

> *[자습서](https://j2doll.github.io/fish-shell-docs-kor/tutorial/)*

> *[디자인](https://j2doll.github.io/fish-shell-docs-kor/design/)*

> *[명령](https://j2doll.github.io/fish-shell-docs-kor/commands/)*

> *[FAQ](https://j2doll.github.io/fish-shell-docs-kor/faq/)*

> *[라이선스](https://j2doll.github.io/fish-shell-docs-kor/license-fish/)*

## 피쉬 쉘 (Fish Shell) 자습서 [입문, 강좌, 소개, 튜토리얼]

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

<pre>
Welcome to fish, the friendly interactive shell
Type <font color="green">help</font> for instructions on how to use fish
you@hostname ~>
</pre>

- 피쉬(fish)는 사용자 이름, 호스트 이름 및 작업 디렉토리를 보여주는 기본 프롬프트(default prompt)와 함께 제공됩니다. 또한 다음 경로에 프롬프트를 변경하는 방법을 기술하고 있습니다. [https://fishshell.com/docs/current/tutorial.html#tut_prompt](https://fishshell.com/docs/current/tutorial.html#tut_prompt)
- 이제부터는 설명하는 공간을 절약하기 위해 프롬프트는 '>' 인 것으로 가정하여 설명하겠습니다.

### 명령 실행 (Running Commands)
- 피쉬(fish)는 다른 쉘과 같은 명령(command)을 실행합니다.
- 명령을 입력하고 인수를 입력하면 됩니다. 백은 구분 기호입니다.

<pre>
> <font color="purple">echo</font> <font color="blue">hello world</font>
hello world
</pre>

- 역 슬래시(\)가 있는 인수에 리터럴(literal) 공백을 포함하거나 작은 따옴표(') 나 큰 따옴표(“)를 사용할 수 있습니다.

<pre>
> <font color="blue">mkdir My\ Files</font>
> <font color="purple">cp</font> <font color="blue">~/Some\ File</font> <font color="brown">'My Files'</font>
> <font color="purple">ls</font> <font color="brown">"My Files"</font>
Some File
</pre>

- 명령은 세미콜론(;)으로 연결될 수 있습니다.

### 도움 받기 (Getting Help)
- 피쉬(fish)는 훌륭한 도움말과 맨(man) 페이지를 가지고 있습니다.
- 웹 브라우저에서 help 을 실행하고 man 페이지에서 help 을 실행하십시오.
- 특정 명령에 대한 도움을 요청할 수도 있습니다.
	- 예: 웹 브라우저에서 열기 위해서 help set, 터미널에서 보기 위해 man set 설정
	
<pre>
> <font color="purple">man</font> <font color="blue">set</font>
set - handle shell variables
  Synopsis...
</pre>

### 구문 강조 (Syntax Highlighting)
- 입력하는 동안 피쉬(fish) 구문 강조를 수행한다는 것을 빨리 알 수 있습니다.
- 잘못된 명령은 기본적으로 <font color="red">빨간색(Red)</font>으로 표시됩니다.

<pre>
> <font color="red">/bin/mkd</font>
</pre>

- 명령이 존재하지 않거나 실행할 수 없는 파일을 참조하기 때문에 명령이 유효하지 않을 수 있습니다. 명령이 유효해지면 다른 색으로 표시됩니다.

<pre>
> <font color="blue">/bin/mkdir</font>
</pre>
 
-  피쉬(fish)는 입력할 때 유효한 파일 경로에 밑줄을 긋습니다.

<pre>
> <font color="purple">cat</font> <font color="blue"><u>~/somefi</u></font>
</pre>
 
- 이것은 'somefi'로 시작하는 파일이 있다는 것을 의미하며, 이는 입력할 때 유용한 피드백입니다.
- 이러한 색상과 그 이상은 fish_config 를 실행하거나 변수를 직접 수정하여 변경할 수 있습니다.

### 와일드 카드 (Wildcards)
- 피쉬(fish)는 익숙한 와일드 카드(*)를 지원합니다.
- 모든 JPEG 파일(*.jpg)을 나열하려면 다음과 같이하십시오.

<pre>
> <font color="purple">ls</font> <font color="blue">*.jpg</font>
 lena.jpg
 meena.jpg
 산타 마리아.jpg
</pre>

- 여러 개의 와일드 카드를 포함 할 수도 있습니다.

<pre>
> <font color="purple">ls</font> <font color="blue">l*.p*</font>
 lena.png
 lesson.pdf
</pre>

- 특히 재귀적으로 디렉토리를 검색하는 재귀적 와일드 카드(**)가 강력합니다.

<pre>
> <font color="purple">ls</font> <font color="blue">/var/**.log</font>
 /var/log/system.log
 /var/run/sntp.log
</pre>

- 해당 디렉토리 탐색에 오랜 시간이 걸리면 Ctrl + C 를 사용하여 중지할 수 있습니다.

### 파이프 및 방향 전환 (Pipes and Redirections)
- 일반적인 세로 막대(\|)를 사용하여 명령 사이를 파이프 할 수 있습니다.

<pre>
> <font color="purple">echo</font> <font color="blue">hello world</font> | <font color="blue">wc</font>
       1       2      12
</pre>

- stdin 및 stdout는 익숙한 < 및 > 를 통해 리디렉션(redirection) 될 수 있습니다.
- 다른 쉘과는 달리 stderr은 캐럿(^)으로 리디렉션됩니다.

<pre>
> <font color="purple">grep</font> <font color="blue">fish</font> < /etc/shells > ~/output.txt ^ ~/errors.txt
</pre>

### 자동 제안 (Auto-suggestions)
- 피쉬(fish)는 사용자가 입력할 때 명령(command)을 제안하고, 커서 오른쪽에있는 제안을 회색으로 표시합니다.

<pre>
> <font color="red">/bin/h</font>ostname
</pre>

- 피쉬는 경로 및 옵션에 대해 알고 있습니다.

<pre>
> <font color="purple">grep</font> <font color="blue">--i</font>gnore-case
</pre>

- 그리고 명령을 한 번 입력하면 기록(history)도 몇자를 입력하여 명령을 다시 불러올 수 있습니다.

<pre class="fish cli-dark"><span class="prompt">&gt;</span> <span class="error"><font color="red">r</font><span class="redirect">&lt;</span></span>\@args{ync} \ <span class="argument"><font color="blue">ssh</font></span> <span class="argument"><font color="blue">.</font></span> <span class="argument"><font color="blue">myname</font></span><span>@</span>somelonghost.com:/some/long/path/doo/dee/doo/dee/doo}
</pre>

- 자동 제안을 수락하려면  → 또는 Control F 를 누르십시오. 
- 자동 제안의 한 단어를 수락하려면  Alt (오른쪽 화살표)를 누르십시오.
- 자동 검색 기능이 원하는 기능이 아닌 경우에는 무시하십시오.

### 탭 완성 (Tab Completions)

- 피쉬(fish)에는 탭(tab) 완성이 풍부하게 갖추어져 있으며, 이는 즉석에서 작동합니다.
- Tab 키를 누르면 피쉬(fish)가 명령, 인수 또는 경로를 완료하려고 시도합니다.

<pre>
> <font color="red">/pri</font> <font color="blue">@key{Tab} → /private/</font>
</pre>

- 둘 이상의 가능성이 있는 경우 목록에 표시됩니다.

<pre>
> <font color="red">~/stuff/s</font> @key{Tab}
~/stuff/script.sh  <font color="grey">(Executable, 4.8kB)</font>  <font/>~/stuff/sources/</font>  (Directory)
</pre>

- Hit tab again to cycle through the possibilities.
- fish can also complete many commands, like git branches:

<pre>
> <font color="purple">git</font> <font color="blue">merge pr</font> @key{Tab} → <font color="purple">git</font> <font color="blue">merge prompt_designer</font>
> <font color="purple">git</font> <font color="blue">checkout b</font> @key{Tab}
builtin_list_io_merge <font color="grey">(Branch)</font> <font color="darkcyan">builtin_set_color</font> <font color="grey">(Branch)</font> <font color="darkcyan">busted_events</font> <font color="grey">(Tag)</font>
</pre>

- 탭을 치고 피쉬(fish)가 할 수 있는 것들을 보십시오!

### 변수 (Variables)

- 다른 쉘과 마찬가지로 달러 기호는 변수 대체를 수행합니다.

<pre>
> <font color="purple">echo</font> <font color="blue">My home directory is</font> <font color="darkcyan">$HOME</font>
My home directory is /home/tutorial
</pre>

- 변수 대입은 큰 따옴표에서도 발생하지만 작은 따옴표에서는 발생하지 않습니다.

<pre>
> <font color="purple">echo</font> <font color="brown">"My current directory is $PWD"</font>
My current directory is /home/tutorial
> <font color="purple">echo</font> <font color="brown">'My current directory is $PWD'</font>
My current directory is $PWD
</pre>

- 다른 쉘과 달리 피쉬(fish)에는 변수 설정을 위한 전용 구문이 없습니다.
- 대신 변수 이름과 그 값을 취하는 일반적인 명령 set 이 있습니다.

<pre>
> <font color="purple">set</font> <font color="blue">name</font> <font color="brown">'Mister Noodle'</font>
> <font color="purple">echo</font> <font color="darkcyan">$name</font>
Mister Noodle
</pre>

- <font color="red">(따옴표를 주의 하십시오! : 그것들이 없으면 Mister와 Noodle은 별도의 인수가 되고 $name은 두 개의 요소 목록으로 만들어집니다.)</font>
- 다른 셸과 달리 변수는 대체 후에 더 이상 분리되지 않습니다.

<pre>
> <font color="blue">mkdir</font> <font color="darkcyan">$name</font>
> <font color="purple">ls</font>
Mister Noodle
</pre>

- bash에서는 두 개의 디렉토리 인 "Mister"와 "Noodle"을 만들었을 것입니다.
- 피쉬(fish)에서는 단지 하나의 경로(Mister Noodle)를 만들었습니다.
- 변수는 "Mister Noodle"이라는 값을 가졌으며, 그것은 mkdir 에 전달된 인수(argument)입니다.
- 다른 셸에서는 목록이 아닌 "배열(array)"이라는 용어를 사용합니다.

### 종료 상태(Exit Status)

- 다른 쉘과 달리 피쉬(fish)는 마지막 명령(last command)의 종료 상태를 $?. 대신 $status 에 저장합니다.

<pre>
> <font color="purple">false</font>
> <font color="purple">echo</font> <font color="darkcyan">$status</font>
1
</pre>

- 반환값이 0인 경우 성공(success)으로 간주되고, 0이 아닌 값은 실패(failure)입니다.

### 내보내기 (셸 변수)

- 다른 쉘과 달리 피쉬(fish)에는 <font color="red">export 명령이 없습니다!</font>
- 대신 변수는 –export 또는 -x 중 하나를 set 하는 옵션을 통해 내보내집니다.
- (set 명령어 활용을 권장합니다!)

<pre>
> <font color="purple">set</font> <font color="blue">-x MyVariable SomeValue</font>
> <font color="purple">env</font> | <font color="purple">grep</font> MyVariable
<font color="drkcyan">MyVariablem</font>=SomeValue
</pre>

- -e 또는—erase 를 사용하여 변수를 지울 수도 있습니다.

<pre>
> <font color="purple">set</font> <font color="blue">-e MyVariable</font>
> <font color="purple">env</font> | <font color="purple">grep</font> <font color="blue">MyVariable</font>
(no output)
</pre>

### 목록(List)
- 위의 set 명령은 Mister Noodle 이 하나의 인수 Mister Noodle 인지 확인하기 위해 따옴표를 사용했습니다. 두 개의 인수가 있었다면 name 은 길이(length)가 2인 목록(list)이었을 것입니다.
- 사실,피쉬(fish)의 모든 변수는 실제로 목록(list)이며, 값의 개수를 포함할 수도 있고, 전혀 포함하지 않을 수도 있습니다.
- $PWD 와 같은 일부 변수에는 하나의 값만 있습니다. 규칙에 따라 변수의 값에 대해 이야기하지만 실제로는 첫 번째 값을 의미합니다.
- $PATH 와 같은 다른 변수에는 실제로 여러 값이 있습니다. 변수 확장 중에는 변수가 확장되어 여러 인수가 됩니다. <font color="red">(경로들간에 콜론(:)이 없는 것을 주목하십시오!)</font>

<pre>
> <font color="purple">echo</font> <font color="darkcyan">$PATH</font>
/usr/bin /bin /usr/sbin /sbin /usr/local/bin
</pre>

- 피쉬(fish)가 실행을 시작할 때 콜론(:)으로 분리된 세 개의 환경 변수인 PATH, CDPATH, MANPATH 가 있습니다.
- 이는 반대로 하위 명령으로 내보낼 때 콜론에 조인됩니다.
- 유사한 의미를 갖는 다른 모든 환경 변수(예: LD_LIBRARY_PATH)는 단순한 문자열로 취급됩니다.
- 목록(list)에는 다른 목록을 포함할 수 없습니다. <font color="red">목록은 재귀가 없습니다!</font>
- 변수는 문자열(string)의 목록(list)이며, 전체 정지입니다.

<pre>
> <font color="purple">count</font> <font color="darkcyan">$PATH</font>
5
</pre>

- 추가 인수를 사용하여 목록 자체를 설정하여 목록에 추가하거나 추가 할 수 있습니다.
- 다음은 /usr/local/bin을 $ PATH에 추가하는 예제입니다.

