# 피쉬 쉘(Fish Shell) 한글화 문서 [비공식]

> *[문서](https://j2doll.github.io/fish-shell-docs-kor/doc/)*

> *[<b>자습서</b>](https://j2doll.github.io/fish-shell-docs-kor/tutorial/)*

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
- 다음은 /usr/local/bin을 $PATH에 추가하는 예제입니다.

<pre>
> <font color="purple">set</font> <font color="blue">PATH</font> <font color="darkcyan">$PATH</font> <font color="blue">/usr/local/bin</font>
</pre>

- 대괄호([])로 개별 요소에 접근 할 수도 있습니다.
- 인덱싱(indexing)은 처음부터 1에서 시작하고, 끝에서 부터는 -1에서 시작합니다.

<pre>
 > <font color="purple">echo</font> <font color="darkcyan">$PATH</font>
/usr/bin /bin /usr/sbin /sbin /usr/local/bin
> <font color="purple">echo</font> <font color="darkcyan">$PATH</font>[1]
/usr/bin
> <font color="purple">echo</font> <font color="darkcyan">$PATH</font>[-1]
/usr/local/bin
</pre>

- 그리고 "조각(slice:)" 이라고 하는 요소 범위에도 접근할 수도 있습니다.

<pre>
> <font color="purple">echo</font> <font color="darkcyan">$PATH</font>[1..2]
/usr/bin /bin
> <font color="purple">echo</font> <font color="darkcyan">$PATH</font>[-1..2]
/usr/local/bin /sbin /usr/sbin /bin
</pre>

- 물론 for 루프(loop)를 사용하여 목록(또는 슬라이스)을 반복 할 수 있습니다.

<pre>
> <font color="purple">for</font> val <font color="purple">in</font> $PATH
    <font color="purple">echo</font> <font color="brown">"entry: $val"</font>
  <font color="purple">end</font>
entry: /usr/bin/
entry: /bin
entry: /usr/sbin
entry: /sbin
entry: /usr/local/bin
</pre>

- 다른 목록이나 문자열에 인접한 목록은 따옴표가 붙지 않는 한 곱집합(cartesian products)으로 확장됩니다 ([변수 확장](https://translate.googleusercontent.com/translate_c?act=url&depth=1&hl=ko&ie=UTF8&prev=_t&rurl=translate.google.co.kr&sl=en&sp=nmt4&tl=ko&u=https://fishshell.com/docs/current/index.html&xid=17259,15700023,15700043,15700105,15700124,15700149,15700168,15700173,15700201&usg=ALkJrhhj-v_8MUZPDBdTkWgs4tPZUoR7Aw#expand-variable) 참조)

<pre>
> <font color="purple">set</font> -l a 1 2 3
> <font color="purple">set</font> -l 1 a b c
> <font color="purple">echo</font> $a$1
1a 2a 3a 1b 2b 3b 1c 2c 3c
> <font color="purple">echo</font> $a" banana"
1 banana 2 banana 3 banana
> <font color="purple">echo</font> "$a banana"
1 2 3 banana
</pre>

- 이는 괄호 확장(Brace Expansion)과 유사합니다. https://fishshell.com/docs/current/index.html#expand-brace

### 명령 확장(Variable expansion)
- 명령 확장은 한 명령의 출력을 다른 명령의 인수로 사용합니다.
- 다른 쉘과는 달리, 피쉬(fish)는 명령 확장을 위해 <font color="red">백틱(\`)을 사용하지 않습니다!</font>
- 대신 괄호()를 사용합니다.

<pre>
> <font color="purple">echo</font> <font color="blue">In</font> (<font color="purple">pwd</font>), <font color="blue">running</font> (<font color="purple">uname</font>)
In /home/tutorial, running FreeBSD
</pre>

- 명령 변수의 출력을 캡처하는 것은 일반적인 관용입니다.

<pre>
> <font color="purple">set</font> os (<font color="purple">uname</font>)
> <font color="purple">echo</font> <font color="darkcyan">$os</font>
Linux
</pre>

- 명령 확장은 따옴표 안에 확장되지 않습니다.
- 대신, 동일한 인수에서 따옴표를 임시로 닫고 명령 대체를 추가한 다음 다시 열 수 있습니다.

<pre>
> <font color="purple">touch</font> <font color="brown">"testing_"</font>(<font color="purple">date</font> <font color="blue">+%s</font>)<font color="brown">".txt"</font>
> <font color="purple">ls</font> <font color="blue">*.txt</font>
testing_1360099791.txt
</pre>

- 다른 쉘과는 달리, 피쉬는 공백이나 공백 같은 명령 공백을 없애지 않습니다!
- 이것은 pkg-config 와 같은 명령으로 한 줄에 여러 개의 인수를 의미하는 내용을 인쇄할 때 문제가 될 수 있습니다.
- 공백으로 분할하려면 string split 을 사용하십시오.

<pre>
> <font color="purple">printf</font> <font color="brown">'%s\n'</font> (<font color="blue">pkg</font>-config <font color="blue">--libs gio-2.0</font>)
-lgio-2.0 -lgobject-2.0 -lglib-2.0
> <font color="purple">printf</font> <font color="brown">'%s\n'</font> (<font color="blue">pkg</font>-config <font color="blue">--libs gio-2.0</font> | <font color="purple">string</font> <font color="blue">split</font> " ")
-lgio-2.0
-lgobject-2.0
-lglib-2.0
</pre>

### 명령 분리 (세미콜론)
- 다른 쉘과 마찬가지로 피쉬(fish)는 별도의 줄 또는 동일한 줄에서 여러 명령을 허용합니다.
- 같은 줄에 쓰려면 세미콜론(;)을 사용하십시오.
- 이는 다음 두 예제가 동일함을 의미합니다

<pre>
<font color="blue">echo</font> fish; <font color="blue">echo</font> chips
\# or
<font color="blue">echo</font> fish
<font color="blue">echo</font> chips
</pre>

### 결합자 (And, Or, Not)
- 다른 쉘과 달리 피쉬(fish)에는 && 또는 \|\| 와 같은 특수 구문이 <font color="red">없습니다!</font>
- 대신에 and, or, not 명령을 가지고 있습니다.

<pre>
> <font color="purple">cp</font> file1.txt file1_bak.txt; <font color="purple">and echo</font> <font color="brown">"Backup successful"</font>; or echo <font color="brown">"Backup failed"</font>
Backup failed
</pre>

- 세미콜론 장절에서 언급했듯이 다음과 같이 여러 줄로 작성할 수도 있습니다.

<pre>
<font color="purple">cp</font> file1.txt file1_bak.txt
and <font color="purple">echo</font> <font color="brown">"Backup successful"</font>
or <font color="purple">echo</font> <font color="brown">"Backup failed"</font>
</pre>

### 조건문 (If, Else, Switch)
-  If, else if 및 else 를 사용하여 명령(command)의 종료 상태에 따라 조건부로 코드를 실행 가능합니다.

<pre>
<font color="purple">if grep</font> fish /etc/shells
    <font color="purple">echo</font> Found fish
<font color="purple">else if grep</font> bash /etc/shells
    <font color="purple">echo</font> Found bash
<font color="purple">else</font>
    <font color="purple">echo</font> Got nothing
<font color="purple">end</font>
</pre>

- 복합자(Combiners)는 또한 다음과 같이 더 복잡한 조건을 만드는 데 사용될 수 있습니다.

<pre>
if grep fish /etc/shells; and command -sq fish
    echo fish is installed and configured
end
</pre>

- 더욱 복잡한 조건의 경우 begin 과 end 를 사용하여 그룹화하십시오.
	- switch 명령도 있습니다.

<pre>
<font color="purple">switch</font> (uname)
<font color="purple">case</font> Linux
    <font color="purple">echo</font> Hi Tux!
<font color="purple">case</font> Darwin
    <font color="purple">echo</font> Hi Hexley!
<font color="purple">case</font> FreeBSD NetBSD DragonFly
    <font color="purple">echo</font> Hi Beastie!
<font color="purple">case</font> '*'
    <font color="purple">echo</font> Hi, stranger!
<font color="purple">end</font>
</pre>

- case 는 (다음 case 구문으로는) 작동되지 않으며(does not fall through), 여러 개의 인수 또는 와일드 카드(*)를 사용할 수 있습니다.
- (예제에서 Linux Fish 인 경우, Hi Tux! 만 출력되며, MSYS Fish 인 경우 Hi, Stranger 가 출력됩니다.)

### 함수 (Function)
- 피쉬 함수(function)는 선택적으로 인자(argument)를 취할 수 있는 명령 목록(list of commands)입니다.
- 다른 쉘과 달리 인수는 $1 과 같은 <font color="red">'번호가 매겨진 변수'로 전달되지 않고</font>, 단일 목록 $argv 됩니다!
- 함수를 만들려면 내장 함수를 사용하십시오.

<pre>
> <font color="purple">function</font> say_hello
          <font color="purple">echo</font> Hello $argv
  <font color="purple">end</font>
> <font color="blue">say_hello</font>
Hello
> <font color="blue">say_hello everybody!</font>
Hello everybody!
</pre>

- 다른 쉘과 달리 피쉬(fish)에는 별칭(alias)이나 특별한 프롬프트 구문(prompt syntax)이 없습니다. 함수가 그들의 자리를 잡습니다.
- functions 키워드를 사용하여 모든 함수의 이름을 나열할 수 있습니다. (복수형(~s)임을 주의!).
- 피쉬(fish)는 많은 함수를 제공합니다.

<pre>
> <font color="purple">functions</font>
alias, cd, delete-or-exit, dirh, dirs, down-or-search, eval, export, fish_command_not_found_setup, fish_config, fish_default_key_bindings, fish_prompt, fish_right_prompt, fish_sigtrap_handler, fish_update_completions, funced, funcsave, grep, help, history, isatty, ls, man, math, nextd, nextd-or-forward-word, open, popd, prevd, prevd-or-backward-word, prompt_pwd, psub, pushd, seq, setenv, trap, type, umask, up-or-search, vared
</pre>

- 함수 이름을 functions 에 전달하면 모든 함수의 소스(source)를 볼 수 있습니다.

<pre>
> <font color="purple">functions</font> <font color="blue">ls</font>
<font color="purple">function</font> <font color="blue">ls</font> --description 'List contents of directory'
    <font color="purple">command ls</font> <font color="blue">-G</font> $argv
<font color="purple">end</font>
</pre>

### 루프 (Loop)
- while 무한 루프 :

<pre>
> <font color="purple">while</font> true
    <font color="purple">echo</font> "Loop forever"
<font color="purple">end</font>
Loop forever
Loop forever
Loop forever
...
</pre>

- For 루프는 목록을 반복하는 데 사용할 수 있습니다.
- 예를 들어, 파일 목록 :

<pre>
> <font color="purple">for</font> file <font color="purple">in</font> *.txt
    <font color="purple">cp</font> $file $file.bak
<font color="purple">end</font>
</pre>

- 명령 seq 을 사용하여 숫자 목록을 반복 할 수 있습니다.

<pre>
> <font color="purple">for</font> x in (<font color="purple">seq</font> 5)
    <font color="purple">touch</font> file_<font color="blue">$x</font>.txt
<font color="purple">end</font>
</pre>

### 프롬프트 (Prompt)
- 피쉬는 다른 셸과 달리 <font color="red">프롬프트 변수는 없습니다!</font> (PS1 처럼)
- 프롬프트를 표시하기 위해 피쉬(fish)는 fish_prompt 라는 이름의 함수를 실행하고, 출력은 프롬프트로 사용됩니다.
- 다음과 같은 나만의 프롬프트도 정의할 수 있습니다.

<pre>
> <font color="purple">function</font> <font color="blue">fish_prompt</font>
    <font color="purple">echo</font> <font color="brown">"New Prompt % "</font>
<font color="purple">end</font>
New Prompt %
</pre>

- 여러 줄은 괜찮습니다.
- set_color 를 통해 색상을 설정하고 ANSI 색상 또는 16 진수 RGB 값을 전달할 수도 있습니다.

<pre>
> <font color="purple">function</font> fish_prompt
      <font color="purple">set_color</font> purple
      <font color="purple">date</font> <font color="brown">"+%m/%d/%y"</font>
      <font color="purple">set_color</font> FF0
      <font color="purple">echo</font> (pwd) <font color="brown">'>'</font>
      <font color="purple">set_color</font> normal
  <font color="purple">end</font>
<font color="red">02/06/13</font>
/home/tutorial >
</pre>

- fish_config prompt 를 실행하여 몇 가지 샘플 프롬프트 중에서 선택할 수도 있습니다.
- 피쉬(fish)는 또한 fish_right_prompt 를 통해 RPROMPT(오른쪽 정렬 프롬프트)를 지원합니다.

### $PATH (경로 변수)

- $PATH는 피쉬(fish)가 명령을 검색하는 디렉토리를 포함하는 환경 변수입니다. 다른 쉘과 달리 $PATH는 콜론으로 구분된 문자열이 아닌 목록(list)입니다.
- /usr/local/bin 과 /usr/sbin 을 $PATH 앞에 추가하려면 다음과 같이 작성할 수 있습니다.

<pre>
> <font color="purple">set</font> <font color="blue">PATH /usr/local/bin /usr/sbin</font> $PATH
</pre>

- $PATH 에서 /usr/local/bin 을 제거하려면 다음과 같이 작성할 수 있습니다.

<pre>
> <font color="purple">set</font> <font color="blue">PATH</font> (<font color="purple">string</font> <font color="blue">match -v /usr/local/bin</font> $PATH)
</pre>

- .profile 파일을 가진 다른 쉘 에서처럼 피쉬는 config.fish 파일에서 직접 작업을 할 수 있습니다. (예제 참조)
- 더 빠른 방법은 $fish_user_paths universal 변수 를 수정하는 $fish_user_paths 을 사용하여 자동으로 $PATH 앞에 추가하는 것입니다. 예를 들어 $PATH 에 /usr/local/bin 을 영구적으로 추가하려면 다음과 같이 작성할 수 있습니다.

<pre>
> <font color="purple">set</font> <font color="blue">-U fish_user_paths /usr/local/bin</font> $fish_user_paths
</pre>

- 이러한 방법의 잇점은 파일에서 수정할 필요가 없다는 것입니다.
- 명령줄에서 이 명령을 한 번 실행하면 현재 세션과 이후의 모든 인스턴스에도 영향을 미칩니다.
- (주의: config.fish 에 이 줄을 추가하면 안됩니다. 그렇게 하면 피쉬를 실행할 때마다 환경 변수가 계속 더 길어집니다!)

### 초기화 (.bashrc는 어디 갔나요?)
- 피쉬(fish) 는 <b>~/.config/fish/config.fish</b> 파일에서 명령을 실행하여 시작합니다.
- 만약 파일이 존재하지 않으면 신규로 생성할 수 있습니다.
- 위에 표시된 명령을 사용하여 config.fish 파일에 함수 및 변수를 직접 작성할 수 있습니다.

<pre>
> <font color="purple">cat</font> ~/.config/fish/config.fish

<font color="purple">set</font> <font color="blue">-x PATH</font> $PATH <font color="blue">/sbin/</font>

<font color="purple">function</font> <font color="blue">ll</font>
    <font color="purple">ls</font> <font color="blue">-lh</font> $argv
<font color="purple">end</font>
</pre>

### 함수 자동 로딩 (Autoloading Functions)
- 피쉬(fish) 가 명령을 만났을 때 ~/.config/fish/functions/ 파일에 있는 명령의 이름을 가진 파일을 찾아 해당 명령에 대한 함수를 자동으로 로드하려고 시도합니다.
- 예를 들어, 함수 ll 을 만들고 싶다면(물론 ll이 없는 경우에 활용하는 방법입니다), ll 함수를 ~/.config/fish/functions 파일에 추가하면 됩니다.

<pre>
> <font color="purple">cat</font> <font color="blue">~/.config/fish/functions/ll.fish</font>
<font color="purple">function</font> <font color="blue">ll</font>
    <font color="purple">ls</font> <font color="blue">-lh</font> $argv
<font color="purple">end</font>
</pre>

- 이것은 프롬프트를 정의하는 기본 방법입니다.

<pre>
> <font color="purple">cat</font> <font color="blue">~/.config/fish/functions/fish_prompt.fish</font>
<font color="purple">function</font> <font color="blue">fish_prompt</font>
    <font color="purple">echo</font> (pwd) "> "
<font color="purple">end</font>
</pre>

- 이러한 파일을 자동으로 만드는 방법은 funced 및 funcsave 설명서를 참조하십시오.

### 범용 변수 (Universal Variables)

<pre>
> <font color="purple">set</font> <font color="blue">-U EDITOR vim</font>
</pre>

- 이제 다른 쉘에서 다음 명령을 실행하여 보십시오.

<pre>
> <font color="purple">echo</font> $EDITOR
<font color="purple">vim</font>
</pre>

### 피쉬를 사용하실 준비되셨습니까?!
- 피쉬에 대해 더 자세히 알고 싶다면 상세한 문서, 공식 메일링 리스트, IRC 채널 #fish (irc.oftc.net) 및 github 페이지가 있습니다. [https://github.com/fish-shell/fish-shell/](https://github.com/fish-shell/fish-shell/)

#### 번역 후기
- 피쉬를 써보니 일단 편합니다!
- 체감적으로 편하다는 것은 열번 정도 누를 키를 서너번만 눌러도 된다는 정도의 편함이라고 이해하시면 될 것 같습니다.
- 시간날때 나머지 글도 번역 예정입니다

#### 미러링된 글
- 다음의 경로에도 수록되어 있습니다.
	- [https://okky.kr/article/454099](https://okky.kr/article/454099)
	- [http://j2doll.tistory.com/563](http://j2doll.tistory.com/563)
- 원본 [https://fishshell.com/docs/current/tutorial.html](https://fishshell.com/docs/current/tutorial.html)

#### 라이선스 주의
- 피쉬 쉘의 소스코드 및 자료는 모두 GPL 라이선스 2 입니다. 쉽게 이야기 해서 해당 코드 및 자료를 사용하면 공개하셔야 합니다.
