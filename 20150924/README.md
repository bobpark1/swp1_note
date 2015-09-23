루비 사용법

1. 시작: 명령어 irb

2.2.2 버전 001 라인 수

2. puts 화면에 텍스트 출력
=> nil return값이 없는 것

3. exit: ruby에서 나오는 것

4. .rb: 루비 파일 확장명
실행 방법: 콘솔 명령어 상태에서 ruby + file명(가령 hellworld.rb; 2개 단어만 입력 후 tab하면 자동 완성이 됨) 

5. 변수 지정: (변수) = (독립변수) (이미 변수로 지정한 것을 독립변수로 사용 가능)
            예약어(명령어)는 변수 이름으로 잡을 수 없다

6. rubymagic.org에 rails reserved words에서 예약어 목록 확인 가능 - drive, format, action은 나중에 많이 쓸 것이다/save, send는 rail는 안되고 ruby는 잘됨
7. database field name을 쓸 때 type같은 거 쓰면 안됨

8. print: puts처럼 텍스트를 출력하지만 줄바꿈은 하지 않음

9. gets.chomp 입력을 받는 것(chomp가 없으면 엔터표시(\n)도 출력됨), 변수로 지정도 가능함

10. if/elsif/else/end

11. 변수 지정시에 = , 수학에서처럼 일치함을 맞추고 싶으면 ==

12. ruby-doc.org 에서 관련 정보를 얻을 수 있음

13. array: arr[1, 3] 1 index부터 3개 = arr[1..3] = arr[1..-3]; 값이 없으면 nil이라고 뜸
            arr.at[0] 해당 index의 값을 불러옴
            arr.fetch[100, "opps"] - 100번쨰를 불러오고 없으면 opps 출력
            arr.first, arr.last
            arr.sample - 랜덤 요소를 하나 불러옴. 여러 샘플은 arr.sample[n]
            c = [1..45].to_a - 1부터 45까지의 array를 만드는 것

14. 반복 방식 - 반드시 end를 추가시켜야 함
    1) 10.times 명령어 : 10번 명령어 발생
    2) |i| 를 iter 명령어에 포함 : 시행 명령에 interation 차수를 포함시킴
    3) 10.upto(20) do |i| (반대로 20.downto(10)): interation No.가 10~20으로 정해

    4) arr.each do |x|: array에 있는 각 요소 x에 대하여 명령 시행
    5) arry.each_with_index do |x|: array의 x와 그 index로 명령 시행
    
    6) loop do: while과 비슷한 문제로, break if로 빠져나올 수 있음

15. ""와 ''는 다르다. ""는 ruby코드가 안에 있으면 실행하지만 ''는 문자 그대로 처리하라는 것

16. hash(dictionary)
    1) dictionary = {key: value, key: value, ...} 형태
    2) key값으로 value를 부르고 싶으면 hash[:key]
    3) 핵심: 배열 안의 해쉬 만드는 것 dict = [{dict}, {dict}, ... ]