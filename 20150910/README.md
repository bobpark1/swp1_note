<text>
rel="stylesheet" CSS 파일을 불러올 때 추가하는 속성
media="all" 모든 디바이스에서 불러올 때 추가하는 속성
href="css/style.css" 불러올 파일(css 폴더 속의 style.css)의 경로

시맨틱 태그란 HTML5에서 새롭게 추가된, 문서의 구조를 만드는 요소입니다.
<header>, <footer>, <nav>, <article>, <aside>, <section> 등이 있습니다.

text-align은 텍스트를 정렬하는 CSS 속성입니다.
margin: out / padding: in

float는 정렬에 관련된 CSS 속성으로 대표적인 속성값으로 left, right가 있습니다.
텍스트를 정렬하는 text-align과 다르게 해당 요소 자체를 정렬합니다.
부유 요소가 됩니다.
해당 요소가 가지고 있는 내용 만큼의 너비를 가지게 됩니다.

overflow 속성의 본래 역할은 영역을 벗어나는 요소들을 어떻게 보여줄 것인지 지정하는 것입니다.
예를 들어 overflow: hidden은 어떤 요소 속의 내용이 너무 많아서 그 요소의 영역에 내용을 다 담아내지 못해서 영역 바깥으로 넘쳐날 경우 넘치는 부분을 보이지 않도록 합니다.
overflow: scroll은 일단 넘치는 부분을 보이지 않게 하되 요소에 스크롤 바를 만들어서 스크롤링을 통하여 볼 수 있도록 합니다.
하지만 이 본래 역할 이외에도 몇 가지 유용한 트릭을 사용할 수 있습니다.
이번 스텝에서도 본래 역할 대신 유용한 트릭 중 한 가지를 사용해보도록 하겠습니다.

strong, b, text-weight: bold - 글씨 두껍게
i, em - 기울임

span: 자체로는 아무 효과 없는 태그이나 style 적용을 위해

href에 #li-tag를 넣는 이유: 우리가 만들고 있는 페이지는 페이지가 한 개이기 때문에 페이지 이동을 할 수 없어서 메뉴 클릭시 해당 section으로 이동하게 하는 것이 우리의 목표였습니다

line-height: 줄 간격 조정

form 태그는 사용자와 상호작용하기 위한 태그입니다.
폼 태그에 로그인 정보 입력 -> 제출 -> 확인 -> 로그인 성공
위와 같은 순서로 이루어지게 됩니다. 사용자 눈에는 보이지 않지만 사용자가 데이터를 입력하고, 이를 서버에서 처리 그 후에 ok 응답을 보내서 로그인에 성공하는 것이지요.

<input type="text"> 와 같은 형태는 한 줄 정도를 입력할 수 있는 텍스트 입력창입니다.
여러 줄의 텍스트를 입력받고 싶을 때는 보통 <textarea>를 사용합니다.
rows와 cols 속성을 이용하여 크기를 조절할 수 있습니다. 단위는 한 글자 입니다.
input type="radio": 여러 가지 항목 중 한가지만 선택할 수 있는 버튼을 만드는 속성입니다.

select 태그는 우리들이 웹페이지에서 잘 알고 있는 요소입니다. 블로그 글을 작성할 때라던지 게시판의 글을 작성할 때.
카테고리를 선택한다던지, 글의 종류를 선택할 때 이 select 라는 것을 보통 사용합니다.
열어서 선택하는 선택지
<select name = "">
	<option value=""> </option>
</select>

input type="submit": type 속성을 submit(제출하다)으로 설정해 놓으면, 제출 버튼이 만들어지게 됩니다.value 속성으로 버튼의 텍스트를 바꿀 수 있습니다.

background: no-repeat; 또는 background-repeat: no-repeat;으로도 사용할 수 있습니다

box-sizing을 border-box로 지정해주면 padding, border 등 요소의 크기를 해칠 수 있는 속성을 지정할 때도 요소의 기존 크기를 유지할 수 있습니다.


CSS 태그마다 :hover {} 설정 시 마우스 올라가면 효과 발생

미디어 쿼리: @media (조건) {CSS} 조건에 해당할 시에만 CSS 발동


------
github 코드

linux 상
    git init: git을 완전히 사용하겠다는 것을 선언 -> 업데이트할 때마다 새 파일을 만드는 게 아니라 바뀐 부분만 정리시킴
    ls -al: 폴더 상 프로그램(.으로 시작하는 숨김파일마저) 보게 함
    git status: 파일들의 상태를 확인 가능
                untrackd(red): git init 선언 후 추적이 되지 않는 파일
                tracted(green): 추적을 하고 있는 것. 바뀐 것과 안바뀐 걸 구분가능?
    
    git add README.md: git init 선언 후 이 파일을 추적하도록 하는 명령어
    git commit -m "first": "first"라는 메시지를 저장한 것
                            코드 수정 후 commit하면 log 따라갈 수 있다
    git log: git에 추적파일을 수정한 시간과 commit한 메시지 확인 가능
    
    이후에 내용 수정시 그 로그 추적이 가능(README.md modifed)
    git diff: 마지막 추적 후 수정된 사항(지워진 거 빨강, 추가된 거 초록) 확인가능, q누르면 나옴
    modified가 된 걸 다시 add하면 승인됨(git add . 하면 모든 untracked를 stage에 올림)
    수정된 것을 나누어서 commit 가능
   
   
C9에서 github에 올리는 방법 

1. Quick setup — if you’ve done this kind of thing before

Set up in Desktop	or	 HTTPS SSH https://github.com/bobpark1/swp1_note.git
We recommend every repository include a README, LICENSE, and .gitignore.

2. …or create a new repository on the command line - 우리는 이거를 사용한다


echo # swp1_note >> README.md
git init
git add README.md
git commit -m "first commit"  --> 두개 같이 하려면 git commit -am "message"
git remote add origin https://github.com/bobpark1/swp1_note.git
git push -u origin master

3. …or push an existing repository from the command line

git remote add origin https://github.com/bobpark1/swp1_note.git
git push -u origin master

4. …or import code from another repository

You can initialize this repository with code from a Subversion, Mercurial, or TFS project.


나중에는 git push만 하면 됨

-------
md의 특징

# h1태그
##### h5 태그

헬로우월드(h1태그)
===============

1. 첫번째 ol
2. 두번쨰 ol

- 첫번쨰 ul
- 두번쨰 ul
- 
헬로우 **월드""

[토이코드](http://toycode.net)

</text>