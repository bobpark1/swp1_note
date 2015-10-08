model: 데이터베이스를 설계하는 것

1. 실행: rails controller 구성을 한 뒤에 만들고, db-migrate에 형성됨
        rails g model (모델명)

2. do |t| 밑으로 t의 t.type :keyname   이렇게 설정하면 된다

3. rails c: 레일스 콘솔 들어가서 테스트 해보기
    모델은 대분자로 시작, 모델.명령어 이렇게 하면 내용을 볼 수 있음
    1) Post 모델의 데이터 몽땅 불러오기
        Post.all
    2) 새로운 데이터 작성하기 (1) - id가 자동 생성
        Post.create(writer: "cyc", content: "Hello, World!")
    3) 새로운 데이터 작성하기 (2) - id를 지정
        pp = Post.new
        pp.writer = "cyc"
        pp.content = "Hello, World!"
        pp.save

4. controller의 각 페이지 def에 model을 넣는 방법(연결지어서 지정한 변수(여기서는 @Post)를 <%= %> 포맷으로 넣으면 됨)
    (예시): controller상(전체 ruby code)
            def index
                @posts = Post.all      : 왼쪽은 html.erb에 넣을 변수, 오른쪽은 model의 ruby 명령어
            end

            html.erb상(전체 html code, ruby code는 <%%> 안에, ruby=>html 치환은 <%=%>
            <% @posts.each do |p| %>
            <li><%= p.writer %> : <%= p.content %></li>
            <% end %>
    
    1) Post 모델에서 id 파라미터로 데이터를 찾아서 @post 변수에 저장하기
    @post = Post.find(params[:id])

    2) 불려온 @post 변수에 해당하는 데이터를 데이터베이스에서 삭제하기
        @post.destroy
        
    3) 데이터베이스 업데이트하기
        @post = Post.find(params[:id])
        @post.writer = "cccc"
        @post.content = "hello"
        @post.save

# @post 대신 pp 등 아무 변수나 써도 됩니다.
# @를 붙이는 이유는 해당 뷰에서도 그 변수를 사용하기 위함이고, pp 등 소문자로만 이뤄진 변수를 사용하면 뷰에서 가져와서 쓸 수 없습니다.
# @변수를 인스턴스 변수라고 부릅니다.

5. form tag를 이용하여 페이지 간 데이터를 주고받는 방법
    <form action="/blog/create">
        <input type="text" name="irum">
        <textarea name="naeyong"></textarea>
        <input type="submit">
    </form>

6. 순서: routes(페이지 간 연결 정의) -> controller(각 페이지의 action 정의창, model의 db와 load, save, delete등 가공을 하여 view에 보내줌;
            1) db에서 받는 방법: 4번 참고
            2) db에 보내는 방법: param[:irum] 이용, 대괄호 안은 html 태그의 name속성으로 지정한 것)
        -> view의 template(controller에서 db를 받아 창에 보여주고, form에서 연결 페이지를 정의해주어 routes로 연결; 
            1) 단 뛰어넘고 싶으면 redirect_to :root 사용)
            2) controller에 보낼 view의 데이터는 페이지상 params는 blog/destroy?id=<%=p.id%> 이런 식)
        -> ...

7. input에 미리 내용 넣기: input tag 안에 value="<%= %>"로 넣기
8. 알아두면 좋은 input type: hidden -> 페이지 간 주고받을 id를 사용자에겐 보이지 않게 하는input
9. html의 pre 태그: 엔터가 그대로 나오게 함

10 루비코드: p.created_at: p라는 변수가 처음 db에 생성된 시간
            p.update_at: p라는 변수가 마지막으로 업데이트된 시간
