rails project
<!--codelion에서 알려준 방법
rails new mvc --skip-bundle 실행 후 mvc 디렉터리로 이동

Gemfile 파일 수정: gem 'therubyracer' 활성화

bundle install 실행

git init을 실행하여, Git 저장소 생성

.gitignore 파일 수정: *.swp 추가

git add .으로, 모든 파일/디렉터리를 Git의 관리 대상으로 추가

git commit -m "first commit" 실행

rails s 실행

작업 터미널을 따로 실행한 뒤, mvc 디렉터리로 이동

크롬을 실행한 뒤, 자신의_도메인:3000으로 접속

앞에서 제작했던 mvc 프로젝트 디렉터리를 바탕으로, 레일스 프로젝트 디렉터리 내의 몇 가지 주요한 특징을 정리하면 다음과 같다. 중요한 특징들이니 확실하게 기억하도록 하자.
app 디렉터리 안에 컨트롤러가 모여있는 controllers 디렉터리와, 뷰 디렉터리가 모여있는 views 디렉터리가 위치해 있다.
app/controllers 디렉터리 안의 home 컨트롤러와, app/views 디렉터리 안의 home 뷰 디렉터리는 반드시 그 이름이 서로 동일하다.
home 컨트롤러 내에서 정의한 hello 액션과, app/views/home 디렉터리 안의 hello.html.erb 뷰 파일은 반드시 그 이름이 서로 동일하다.
라우트 규칙을 지정하는 routes.rb 파일은 config 디렉터리 안에 위치해 있다.
-->

수업에서 알려주는 방법
1. rails g controller home:
2. 사용할 폴더/파일: app/controller/home_controller.rb, -> app/views/home/,  -> config/routes.rb
    1) controller에 페이지를 함수로 지정(함수의 이름은 반드시 페이지의 이름과 동일해야 한다)
    2) home/ 폴더에 새 페이지를 .html.erb파일로 만들기(embedded ruby의 약자)
    3) routes.rb를 vi editor을 이용해 get '/' => 'home#index' 즉, 주소창에 도메인만 치는 거는 모두 views 폴더에서 home#index(.html)로 라우팅시켜주는 것
        이 부분에서 어떻게든 views 에 대한 ruby action을 정의해주어야 한다
        /home 에서 /about으로 연결시켜주고 싶으면 get '/about' => 'home#about' 위에 정의가 없으면 get 'home/about' => 'home#about'
3. <%= %>: 이 안에 식은 루비로 해석을 하겠다는 것이고, 여기 들어가는 변수들은 controller에서 정의해줌(단, html은 element 표시가 없으면 이어쓰기를 함)
4. layout에서 수정을 할 경우 모든 페이지에 들어갈 요소를 넣을 수 있다
    e.g. <a href = '/'>home</a> 하면 home 링크를 만들 수 있는 것


5. scaffold 이용하기: rails g scaffold name:string contact_number:string id는 순서에 따라 자동 저장됨
                    rake routes를 치면 모든 링크를 확인할 수 있는데, 그 중 scaffold를 통해 CRUD 작업을 할 수 있는 루트를 확인가능함,
                    db/migrate 내의 파일에서 변수 수정, 저장 후 rake db:drop 후 rake db:migrate를 꼭 해주어야 한다