---
title: "Python practise"
excerpt: "Python basic"
last_modified_at: 2021-09-23T08:48:05-04:00
redirect_from:
  - /theme-setup/
toc: true
---



복합대입 연산자

a += 10  -> a = a + 10
숫자 복합 연산자
+= 숫자 덧셈 후 대입
-= 숫자 뺄셈 후 대입
*= 숫자 곱셈 후 대입
/= 숫자 나눗셈 후 대입
%= 숫자의 나머지를 구한 후 대입
**= 숫자 제곱 후 대입

number = 100
number += 10
number += 20
number += 30
print("number:", number)


문자열 복합 대입 연산자
+= 문자열 연결 후 대입
*= 문자열 반복 후 대입

string = "안녕하세요"
string += "!"
string += "!"
print("string:", string)


사용자 입력: input()
명령 프롬프트에서 사용자로부터 데이터를 입력받을 때 input() 함수를 사용
() 안에 입력한 내용을 프롬프트 문자열이라고 하며, 사용자로부터 입력을 요구하는 안내 내용을 포함한다.

input() 함수로 사용자 입력 받기
string = input("인사말을 입력하세요>")
print(string)

input() 함수의 입력 자료형
print(type(string))


number = input("숫자를 입력하세요.")
print(number)
print(type(number))


입력을 받습니다.
string = input("입력>")
# 출력합니다.
print("자료:", string)
print("자료형:", type(string))


문자열을 숫자로 바꾸기
int() : 문자열을 int 자료형으로 변환. int는 정수를 의미
flot() : 문자열을 float 자료형으로 변환. float는 실수 또는 부동 소수점을 의미

# int() 활용
string_a = input("입력A> ")
int_a = int(string_a)

string_b = input("입력B> ")
int_b = int(string_b)

print("문자열 자료:", string_a + string_b)
print("숫자 자료:", int_a + int_b)

output_a = int("52")
output_b = float("52.273")

print(type(output_a), output_a)
print(type(output_b), output_b)


# int()와 float() 조합하기
input_a = float(input("첫 번째 숫자> "))
input_b = float(input("두 번째 숫자> "))

print("덧셈 결과:", input_a + input_b)
print("뺄셈 결과:", input_a - input_b)
print("곱셈 결과:", input_a * input_b)
print("나눗셈 결과:", input_a / input_b)


숫자를 문자열로 바꾸기
str() : 다른 자료형의 값을 str() 함수의 매개변수에 넣으면 문자열로 변환된다.

output_a = str(52)
output_b = str(52.273)
print(type(output_b), output_b)
print(type(output_b), output_b)


inch 단위의 자료를 입력 받아 cm 단위를 구하는 코드

str_input = input("숫자 입력> ")
num_input = float(str_input)

print()
print(num_input, "inch")
print((num_input * 2.54), "cm")


원의 반지름을 입력받아 원의 둘레와 넓이를 구하는 코드
둘레 : 2 * 원주율 * 반지름
넓이 : 원주율 * 반지름 * 반지름

str_input = input("원의 반지름 입력>")
num_input = float(str_input)

print()
print("반지름:", num_input)
print("둘레:", 2 * 3.14 * num_input)
print("넓이:", 3.14 * num_input ** 2)


변수 교체 (swap)
a = input("문자열 입력>")
b = input("문자열 입력>")

print(a, b)
c = a
a = b
b = c
print(a, b)


문자열의 format() 함수
format() 함수로 숫자를 문자열로 변환하는 몇 가지 형태
format() 함수는 문자열이 가지고 있는 함수. 
중괄호 {}를 포함한 문자열 뒤에 마침표(.)를 찍고 format()을 사용하는데,
중괄호의 개수와 format 함수 괄호 안 매개변수의 개수는 반드시 같아야 한다.

ex)
"{}".format(10)
"{}{}".format(10, 20)
"{}{}{}{}{}".format(101, 202, 303, 404, 505)
이러한 형태로 함수를 사용하면 앞쪽에 있는 문자열의 {}기호가 format() 함수 괄호 안에 있는
매개변수로 차례로 대치되면서 숫자가 문자열이 되는 것.
즉 아래의 예시에서 10은 문자열의 중괄호 부분에 들어가 숫자 10이 문자열 "10"이 되는 것.

# format() 함수로 숫자를 문자열로 변환하기
string_a = "{}".format(10)

# 출력하기
print(string_a)
print(type(string_a))


# format() 함수의 다양한 형태

# format() 함수로 숫자를 문자열로 변환하기
format_a = "{}만 원".format(5000)
format_b = "파이썬 열공하여 첫 연봉 {}만 원 만들기".format(5000)
format_c = "{} {} {}".format(3000, 4000, 5000)
format_d = "{} {} {}".format(1, "문자열", True)

# 출력하기
print(format_a)
print(format_b)
print(format_c)
print(format_d)

indexError 예외
{} 기호의 개수가 format() 함수의 매개변수 개수보다 많으면 indexError 예외가 발생한다.
A = "{} {}".format(1, 2, 3, 4, 5)
print(A)
출력 --> 1 2

B = "{} {} {}".format(1, 2)
print(B)
출력 --> IndexError: Replacement index 2 out of range for positional args tuple


정수를 특정 칸에 출력하기

# 1. 정수
output_a = "{:d}".format(52)  # {:d} 는 int 자료형의 정수를 출력하겠다고 직접적으로 지정하는 것. 매개변수로 정수만 가능

# 2. 특정 칸에 출력하기
output_b = "{:5d}".format(52)  # 5칸을 잡고 뒤에서 부터 52라는 숫자를 채운다.
output_c = "{:10d}".format(52) # 10칸을 잡고 뒤에서 부터 52라는 숫자를 채운다.

# 빈칸을 0으로 채우기
output_d = "{:05d}".format(52) # 5칸 잡고 뒤에서 부터 52넣고 앞의 빈곳은 0처리
output_e = "{:05d}".format(-52) # 5칸 잡고 뒤에서 부터 52넣고 맨 앞자리는 부호로 나머지 빈곳은 0처리

print("# 기본")
print(output_a)
print("# 특정 칸에 출력하기")
print(output_b)
print(output_c)
print("# 빈칸을 0으로 채우기")
print(output_d)
print(output_e)



REF.
변수(variable)를 문자열(string)과 함께 출력할 때는
연결(concatenating) 방식을 사용한다.
이 때 %를 사용한다. % 뒤에 어떤 알파벳을 붙이느냐에 따라 그 형태가 달라진다.

%f     실수(float)
%d     정수(integer)
%s     문자열(string)

name = "Amy"
print("Hello %s" %(name))


기호와 함께 출력하기
output_f = "{:+d}".format(52) # 양수
output_g = "{:+d}".format(-52) # 음수
output_h = "{: d}".format(52) # 양수 : 기호 부분 공백
output_i = "{: d}".format(-52) # 음수 : 기호 부분 공백

print("# 기호와 함께 출력하기")
print(output_f)
print(output_g)
print(output_h)
print(output_i)


조합하기
output_h = "{:+5d}".format(52) # 기호를 뒤로 밀기: 양수
output_i = "{:+5d}".format(-52) # 기호를 뒤로 밀기: 음수
output_j = "{:=+5d}".format(52) # 기호를 앞으로 밀기: 양수
output_k = "{:=+5d}".format(-52) # 기호를 앞으로 밀기: 음수
output_l = "{:+05d}".format(52) # 0으로 채우기: 양수
output_m = "{:+05d}".format(-52) # 0으로 채우기: 음수

print("# 조합하기")
print(output_h)
print(output_i)
print(output_j)
print(output_k)
print(output_l)
print(output_m)

기호와 공백을 조합할 때는 = 기호를 앞에 붙일 수 있다. 
이는 5칸의 공간을 잡았을 때 기호를 빈칸 앞에 붙일 것인지,
숫자 앞에 붙일 것인지 지정하는 기호이다.


부동 소수점 출력의 다양한 형태

float 자료형 기본
float 자료형 출력을 강제로 지정할 때는 {:f}를 사용함.
output_a = "{:f}".format(52.273)
output_b = "{:15f}".format(52.273) # 15칸 만들기
output_c = "{:+15f}".format(52.273) # 15칸에 부호 추가하기
output_d = "{:+015f}".format(52.273) # 15칸에 부호 추가하고 0으로 채우기

print(output_a)
print(output_b)
print(output_c)
print(output_d)


부동 소수점의 경우 소수점 아래 자릿수를 지정하는 기능이 있다.
다음의 코드처럼 '.'을 입력하고뒤에 몇 번재 자릿수까지 표시할 지 지정하면 된다. 
이때 자동으로 반올림 처리를 함.
output_a = "{:15.3f}".format(52.273)
output_b = "{:15.2f}".format(52.273)
output_c = "{:15.1f}".format(52.273)

print(output_a)
print(output_b)
print(output_c)


의미 없는 소수점 제거하기
파이썬은 0과 0.0을 출력했을 때 내부적으로 자료형이 다르므로 서로 다른 값으로 출력한다.
그런데 의미 없는 0을 제거한 후 출력하고 싶을 때는 {:g}를 사용한다.
output_a = 52.0
output_b = "{:g}".format(output_a)

print(output_a)
print(output_b)


# 대소문자 바꾸기 
a = "Hello Python Programming...!"
a.upper()
print(a.upper())
# HELLO PYTHON PROGRAMMING...!
a.lower()
print(a.lower())
# hello python programming...!


문자열 양옆의 공백 제거하기
strip() : 문자열 양옆의 공백 제거
lstrip() : 왼쪽 공백 제거
rstrip() : 오른쪽 공백 제거
여기서 공백이란 띄어쓰기, 탭, 줄바꿈을 모두 포함함.

# """" 또는 ''' = 여러 줄 문자열을 입력할 때 사용하는 것으로
# 보기 쉽게 하려고 다음과 같이 코드를 작성하면 문자열 위아래에 의도하지 않은 줄바꿈이 들어간다.

input_a = """
    안녕하세요
문자열의 함수를 알아봅니다
"""
print(input_a)
# >>>>     
#   안녕하세요
# 문자열의 함수를 알아봅니다

print(input_a.strip())
# >>>>
# 안녕하세요
# 문자열의 함수를 알아봅니다

# 이러한 공백제거 기능을 trim 이라고도 한다.



문자열의 구성 파악하기 : isOO()
isalnum() : 알파벳 or 숫자 확인
isalpha() : 알파벳 확인
isdentifier() : 문자열이 식별자로 사용할 수 있는지 확인
isdecimal() : 문자열이 정수 형태인지 확인
isdigit() : 숫자로 인식 될 수 있는지 확인
isspace() : 공백으로만 구성되어 있는지 확인
islower() : 소문자로만 구성되어 있는지 확인
isupper() : 대문자로만 구성되어 있는지 확인

print("TrainA10".isalnum())
print("10".isdigit())


문자열 찾기
find() : 왼쪽부터 찾아서 처음 등장하는 위치를 찾는다.
rfind() : 오른쪽부터 찾아서 처음 등장하는 위치를 찾는다.

output_a = "안녕안녕하세요".find("안녕")
print(output_a)

output_b = "안녕안녕하세요".rfind("안녕")
print(output_b)


in 연산자
문자열 내부에 어떤 문자열이 있는지 확인 할 때
출력은 True or False

print("안녕" in "안녕하세요")
print("잘자" in "안녕하세요")


split() : 문자열 자르기
다음 예제에서는 split 함수 괄호 안의 문자열인 공백(띄어쓰기)를 기준으로 자른다.
a = "10 20 30 40 50".split(" ")
print(a)


불 만들기 : 비교 연산자
== : 같다
!= : 다르다
< : 작다
> : 크다
<= : 작거나 같다
>= : 크거나 같다

print(10 == 100)
print(10 != 100)
print(10 < 100)
print(10 > 100)
print(10 <= 100)
print(10 >= 100)


문자열 비교 연산자
이때 한글은 가나다 순으로 
print("가방" == "가방")
print("가방" != "가방")
print("가방" < "하마")
print("가방" > "하마")

범위 구하기
x = 25
print(10 < x < 30)
print(40 < x < 60)


not 연산자 조합

x = 10
under_20 = x < 20
print("under_20:", under_20)
print("not under_20:", not under_20)


조건문

number = input("정수 입력> ")
number = int(number)

# 양수 조건
if number > 0:
    print("양수입니다.")

# 음수 조건
if number < 0:
    print("음수입니다.")

# 0 조건
if number == 0:
    print("0 입니다.")


# 날짜/시간 출력

# 날짜/시간 가져오기
import datetime

# 현재 날짜/시간 구하기
now = datetime.datetime.now()

# 출력하기
print(now.year, "년")
print(now.month, "월")
print(now.day, "일")
print(now.hour, "시")
print(now.minute, "분")
print(now.second, "초")


날짜/시간 & format() 활용

import datetime
now = datetime.datetime.now()

print("{}년 {}월 {}일 {}시 {}분 {}초".format(\
    now.year,
    now.month,
    now.day,
    now.hour,
    now.minute,
    now.second
    ))


오전 오후 구분

import datetime
now = datetime.datetime.now()

if now.hour < 12:
    print("현재 시간은 {}시로 오전입니다.".format(now.hour))
if now.hour > 12:
    print("현재 시각은 {}시로 오후입니다.".format(now.hour))


계절 구분

import datetime
now = datetime.datetime.now()

if 3 <= now.month <= 5:
    print("이번 달은 {}월로 봄입니다.".format(now.month))
if 6 <= now.month <= 8:
    print("이번 달은 {}월로 여름입니다.".format(now.month))
if 9 <= now.month <= 11:
    print("이번 달은 {}월로 가을입니다.".format(now.month))
if now.month == 12 or 1 <= now.month <= 2:
    print("이번 달은 {}월로 겨울읍니다.".format(now.month))



# 컴퓨터의 조건
# 

number = input("정수 입력> ")
last_character = number[-1] # 마지막 자리 숫자 추출
last_number = int(last_character)

# 짝수 확인 
if last_number == 0 \
    or last_number == 2 \
    or last_number == 4 \
    or last_number == 6 \
    or last_number == 8:
    print("짝수입니다.")

# 홀수 확인
if last_number == 1 \
    or last_number == 3 \
    or last_number == 5 \
    or last_number == 7 \
    or last_number == 9:
    print("홀수입니다.")


in 문자열 연산자를 활용해서 짝수와 홀수 구분

number = input("정수 입력> ")
last_character = number[-1]

if last_character in "02468":
    print("짝수입니다.")
if last_character in "13579":
    print("홀수입니다.")


나머지 연산자를 활용해 짝수와 홀수 구분

number = input("정수 입력> ")
number = int(number)

if number % 2 == 0:
    print("짝수입니다.")
if number % 2 == 1:
    print("홀수입니다.")


else 활용

number = input("정수 입력> ")
number = int(number)

if number % 2 == 0:
    print("짝수입니다.")
else:
    print("홀수입니다.")


elif : 세 개 이상의 조건을 연결해서 사용 할 때.
if 조건A:
    조건A가 참일 때 실행할 문장
elif 조건B:
    조건B가 참일 때 실행할 문장
elif 조건C:
    조건C가 참일 때 실행할 문장

...
else:
    모든 조건이 거짓을 때 문장



elif 활용 계절 구하기

import datetime

now = datetime.datetime.now()
month = now.month

if 3 <= month <= 5:
    print("현재는 봄입니다.")
elif 6 <= month <= 8:
    print("현재는 여름입니다.")
elif 9 <= month <= 11:
    print("현재는 가을입니다.")
else:
    print("현재는 겨울입니다.")



조건문 구현(1)

score = float(input("학점 입력> "))

if score == 4.5:
    print("신")
elif 4.2 <= score <= 4.5:
    print("교수님의 사랑")
elif 3.5 <= score <= 4.2:
    print("현 체제의 수호자")
elif 2.8 <= score <= 3.5:
    print("일반인")
elif 2.3 <= score <= 2.8:
    print("일탈을 꿈꾸는 소시민")
elif 1.75 <= score <= 2.3:
    print("오락문화의 선구자")
elif 1.0 <= score <= 1.75:
    print("불가촉천민")
elif 0.5 <= score <= 1.0:
    print("자벌레")
elif 0 <= score <= 0.5:
    print("플랑크톤")
elif score == 0:
    print("시대를 앞서가는 혁명의 씨앗")


조건문 구현(2) 
score = float(input("학점 입력> "))

if score == 4.5:
    print("신")
elif 4.2 <= score:
    print("교수님의 사랑")
elif 3.5 <= score:
    print("현 체제의 수호자")
elif 2.8 <= score:
    print("일반인")
elif 2.3 <= score:
    print("일탈을 꿈꾸는 소시민")
elif 1.75 <= score:
    print("오락문화의 선구자")
elif 1.0 <= score:
    print("불가촉천민")
elif 0.5 <= score:
    print("자벌레")
elif 0 <= score:
    print("플랑크톤")
elif score == 0:
    print("시대를 앞서가는 혁명의 씨앗")


False로 변환되는 값

if 조건문의 매개변수에 볼이 아닌 다른 값이 올 때는 자동으로 불로 변환해서 처리함.
따라서 어떤 값이 True로 변환되고, 어떤 값이 False로 변환되는지 알고 있어야 코드를 이해할 수 있다.

False로 변환되는 값은 None, 숫자 0과 0.0, 
빈 컨테이너(빈 문자열, 빈 바이트열, 빈 리스트, 빈 튜플, 빈 딕셔너리 등)
이 외에는 모두 True로 변환 된다.


print("# if 조건문에 0 넣기")
if 0:
    print("0은 True로 변환합니다.")
else:
    print("0은 False로 변환합니다.")
print()

print("# if 조건문에 빈 문자열 넣기")
if "":
    print("빈 문자열은 True로 변환됩니다.")
else:
    print("빈 문자열은 False로 변환됩니다.")



pass

number = input("정수 입력> ")
number = int(number)

if number > 0:
    pass
else:
    pass

raise NotimplementError : 강제 오류 발생

number = input("정수 입력> ")
number = int(number)

if number > 0:
    raise NotimplementError
else:
    raise NotimplementError


리스트와 반복문
리스트는 [] 내부에 여러 종류의 자료를 넣어 선언함.
선언한 리스트를 출력하면 내부의 자료를 모두 출력함.

array =[273, 32, 103, "문자열", True, False]
print(array)

리스트 선언하고 요소에 접근하기
[] 안에 넣는 자료를 요소(element)라한다.
[element, element, element...]

리스트 안에 있는 요소를 각각 사용하려면 리스트 이름 바로 뒤에 []를 입력하고
자료의 위치를 나타내는 숫자를 입력.

list_a = [273, 32, 103, "문자열", True, False]
#         [0] [1]  [2]    [3]     [4]    [5]
# 이때 리스트 기호인 [] 안에 들어간 숫자를 인덱스(index)라고 부른다.
print(list_a[0])
print(list_a[1])
print(list_a[1:3])

리스트의 특정 요소는 변경할 수 있다. 
다음과 같이 "변경"이라는 문자열을 0번째에 대입하면서 요소를 변경할 수 있음

list_a = [273, 32, 103, "문자열", True, False]
list_a[0] = "변경"
print(list_a)
# >>>> ['변경', 32, 103, '문자열', True, False]

[]안에 음수를 넣어 뒤에서부터 요소를 선택할 수 있다.
list_a = [273, 32, 103, "문자열", True, False]
print(list_a[-1])
print(list_a[-2])
print(list_a[-3])

리스트 접근 연산자를 다음과 같이 이중으로 사용할 수 있다.
list_a = [273, 32, 103, "문자열", True, False]
print(list_a[3][0]) # >>> 문
3번째에 가져온 "문자열"에서 다시 0번째를 가져와 출력.

리스트 안에 리스트 사용 가능.
아래와 같이 기술하면 list_a는 리스트 세 개를 가지는 리스트로 만들어짐
list_a = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(list_a[1])
print(list_a[1][1])
print(list_a[2][2])


리스트 연산자 : 연결(+), 반복(*), len()

# 리스트 선언
list_a = [1, 2, 3]
list_b = [4, 5, 6]

# 출력
print("# 리스트")
print("list_a =", list_a)
print("list_b =", list_b)
print()

# 기본 연산자
print("# 리스트 기본 연산자")
print("list_a = list_b =", list_a + list_b)
print("list_a * 3 =", list_a * 3)
print()

# 함수
print("# 길이 구하기")
print("len(list_a) =", len(list_a))
# len() 함수는 괄호 내부에 문자열을 넣으면 문자열을 글자 수(=길이)를 세어주지만, 
# 리스트 변수를 넣으면 요소의 개수를 세어 준다.


리스트에 요소 추가하기
append() : 리스트 뒤에 요소를 추가
리스트명.append(요소)
insert() : 리스트의 중간에 요소를 추가
리스트명.insert(위치, 요소)

# 리스트 선언
list_a = [1, 2, 3]

# 리스트 뒤에 요소 추가하기
print("# 리스트 뒤에 요소 추가하기")
list_a.append(4)
list_a.append(5)
print(list_a)
print()

# 리스트 중간에 요소 추가하기
print("# 리스트 중간에 요소 추가하기")
list_a.insert(0, 10)
print(list_a)

append()와 insert()는 리스트에 요소 '하나'를 추가한다.
한 번에 여러 요소를 추가하고 싶을 때는 extend()를 사용.
extend()는 매개변수로 리스트를 입력하는데 원래 리스트 뒤에 새로운 리스트의 요소를 모두 추가함

list_a = [1, 2, 3]
list_a.extend([4, 5, 6])
print(list_a)

리스트 연결 연산자와 요소 추가의 차이

list_a = [1, 2, 3]
list_b = [4, 5, 6]
print(list_a + list_b)
print(list_a)
print(list_b) # list_a와 list_b는 어떠한 변화도 없다(비파괴적 처리)

list_a = [1, 2, 3]
list_b = [4, 5, 6]
print(list_a.extend(list_b)) # 실행결과로 아무것도 출력하지 않는다.
print(list_a) # 앞에 입력했던 list_a 자체에 직접적인 변화가 생김
print(list_b)

리스트와 같이 원본에 어떠한 영향도 주지 않는 것을 '비파괴적'이라 표현하고
append(), insert(), extend()와 같이 리스트에 직접적인 영향을 주는 함수 또는 연산자를 '파괴적'이라함



리스트에 요소 제거하기

1. 인덱스로 제거하기 : del, pop / 요소의 위치를 기반으로 요소를 제거

del 키워드는 다음과 같은 구문을 사용하며, 리스트의 특정 인덱스에 있는 요소를 제거함
del 리스트명[인덱스]
pop() 또한 제거할 위치에 있는 요소를 제거하는데, 매개변수를 입력하지 않으면 마지막 요소를 제거함
리스트명.pop(인덱스)

# 리스트 연결 연산자와 요소 추가의 차이
list_a = [0, 1, 2, 3, 4, 5]
print("# 리스트의 요소 하나 제거하기")


# 제거 방법[1] - del
del list_a[1]
print("del list_a[1]:", list_a) # 인덱스가 1번째이므로, 1이 제거

# 제거 방법[2] - pop()
list_a.pop(2)
print("pop(2):", list_a) # 2번째 요소를 제거하라고 했으므로 3이 제거
# pop() 함수의 매개변수에 아무 것도 입력하지 않으면 자동으로 -1이 들어가는 것으로 취급, 마지막 요소를 제거함

del은 범위를 지정해 리스트이 요소를 한꺼번에 제거 가능
[3:6]을 지정하면 마지막 요소를 포함하지 않는다

list_b = [0, 1, 2, 3, 4, 5, 6]
del list_b[3:6]
print(list_b)

범위의 한쪽을 입력하지 않으면 지정한 위치를 기준으로 한쪽 전부 제거 가능
[:3]을 지정하면 3을 기준(3번째 불포함)으로 왼쪽을 모두 제거함

list_c = [0, 1, 2, 3, 4, 5, 6]
del list_c[:3]
print(list_c)

[3:]을 지정하면 3일 기준(3번째 포함)으로 오른쪽 모두 제거
list_d = [0, 1, 2, 3, 4, 5, 6]
del list_d[3:]
print(list_d)



2. 값으로 제거하기 
remove() : 값을 지정해서 제거하는 방식
리스트.remove(값)

list_c = [1, 2, 1, 2]
list_c.remove(2)
print(list_c)
# 지정한 값이 리스트 내부에 여러 개 있어도 가장 먼저 발견되는 하나만 제거함
# 리스트에 중복된 여러 개의 값을 모두 제거하려면 반복문과 조합해서 사용해야 함.

모두 제거하기 : clear()
리스트.clear()

list_d = [0, 1, 2, 3, 4, 5]
list_d.clear()
print(list_d)


리스트 내부에 있는지 확인
in / 값 in 리스트

list_a = [273, 32, 103, 57, 52]
print(273 in list_a)
print(99 in list_a)
print(100 in list_a)
print(52 in list_a)

리스트 내부에 해당 값이 없는지 확인

list_a = [273, 32, 103, 57, 52]
print(273 not in list_a)
print(99 not in list_a)
print(100 not in list_a)
print(52 not in list_a)



for 반복문

for i in range(100):
    print("출력")

앞서 배운 여러 개의 값을 나타낼 수 있게 해주는 리스트와 같은 자료를 사용해서 
반복문을 적용하는 것이 반복문의 기본.

for 반복문: 리스트와 함께 사용하기

for 반복자 in 반복할 수 있는 것: --> 문자열, 리스트, 딕셔너리, 범위 등
    코드

리스트 선언
array = (273, 32, 103, 57, 52)

# 리스트에 반복문을 적용합니다.
for element in array:
    # 출력
    print(element)

for 반복문의 리스트에 있는 요소 하나하나가 element라는 변수에 들어가며
차례차례 반복하게 됨.

for 반복문과 문자열
문자열을 for 반복문 뒤에 넣으면 글자 하나하나에 반복이 적용 된다.

for character in "안녕하세요":
    print("-", character)

list_a = [0, 1, 2, 3, 4, 5, 6, 7]

list_a.extend(list_a)
print(list_a)

list_a.append(10)
print(list_a)

list_a.insert(3, 0)
print(list_a)

list_a.remove(3)
print(list_a)

list_a.pop(3)
print(list_a)

list_a.clear()
print(list_a)


if 조건문의 조건식을 채워서 100 이상의 숫자만 출력하게 만들기

numbers = [273, 103, 5, 32, 65, 9, 72, 800, 99]

for number in numbers:
    if number > 100:
        print("- 100 이상의 수:", number)
        

다음 빈칸을 채워서 실행결과에 해당하는 프로그램 작성하시오.

numbers = [273, 103, 5, 32, 65, 9, 72, 800, 99]

for number in numbers:
    if number - 1 == 02:
        print("{} 는 짝수입니다.")
    else:
        print("{} 는 홀수입니다.")



딕셔너리와 반복문
리스트가 '인덱스를 기반으로 값을 저장하는 것'이라면
딕셔너리는 '키를 기반으로 값을 저장하는 것'

{
    "키A": 10, # 문자열을 키로 사용하기
    "키B": 20,
    "키C": 30,
    1: 40, # 숫자를 키로 사용하기
    False: 50 # 불을 키로 사용하기
}

자료형      의미                        가르키는 위치       선언형식
리스트      인덱스를 기반으로 값을 저장     인덱스             변수=[]
딕셔너리    키를 기반으로 값을 저장         키                 변수={}


딕셔너리 선언하기
딕셔너리는 {}로 선언하며, '키: 값' 형태를 쉼표(,)로 연결해서 사용
키는 문자열, 숫자, 불 등으로 선언 할 수 있다.

EX)
변수 = {
    키: 값,
    키: 값,
    ...
    키: 값
}

dict_a = {
    "name": "어벤져스 엔드게임",
    "type": "히어로 무비"
}

# 인터랙티브 셀에서 딕셔너리를 만들 때는 위의 코드 처럼 닫는 활호가 들여쓰기 뒤에 붙게 작성할 수밖에 없다.
# 파일에 딕셔너리를 작성할 때는 괄호 앞에 들여쓰기를 넣지 않아도 됨.

print(dict_a)

# 딕셔너리의 요소에 접근하기
# 특정 키만 따로 출력 가능.
# 딕셔너리 요소에 접근 할 때는 리스트처럼 딕셔너리 뒤에 []를 입력하고 내부에 인덱스처럼 키를 입력
# 딕셔너리 선언은 {}, 딕셔너리 요소 접근은 []를 입력하고 내부에 인텍스 처럼 키를 입력

print(dict_a["name"])
print(dict_a["type"])

딕셔너리 내부의 값에 문자열, 숫자, 볼 등의 다양한 자료 넣을 수 있다.
리스트와 딕셔너리도 하나의 자료이므로, 리스트와 딕셔너리를 값으로 넣을 수도 있다.

dict_b = {
    "director": ["안소니 루소", "조 루소"],
    "cast": ["아이언맨", "타노스", "토르", "닥터스트레인지", "헐크"]
}

print(dict_b)
print(dict_b["director"])


요소에 접근하는 방법은 리스트와 거의 비슷하다
구분     선언 형식    사용 예        틀린 예
리스트   list_a = []  list_a[1]
딕셔너리 dict_a = []  dict_a["name"] dict_a{"name"}


# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임",
    "ingredient": ["망고", "설탕", "메타중아황산나트륨", "치자황색소"],
    "origin": "필리핀"
}

# 출력
print("name:", dictionary["name"])
print("type:", dictionary["type"])
print("ingredient:", dictionary["ingredient"])
print("origin:", dictionary["origin"])
print()

# 값을 변경
dictionary["name"] = "8D 건조 망고"
print("name:", dictionary["name"])

# ingredient는 dictionary의 키이기도 하지만,
# 여러개의 자료를 가지고 있는 리스트이기도 하므로 
# 다음과 같이 인덱스를 지정하여 리스트 안의 특정 값을 출력 가능

print()
print(dictionary["ingredient"])
print(dictionary["ingredient"][1])


# 딕셔너리의 문자열 키와 관련된 실수(예외처리)

dict_key = {
    name: "7D 건조 망고",
    type: "당절임"
}

# print("name:", dict_key["name"])

# NameError: name 'name' is not defined
# 파이썬은 딕셔너리의 키에 단순한 식별자를 입력하면 이를 변수로 인식함
# 오류 자체를 해결하고 싶다면 name라는 이름을 변수로 만들면 된다.
# type은 type() 함수라는 기본 식별자가 있기 때문에 이것이 키로 들어가 따로 오류를 발생하지는 않는다.

name = "이름"
dict_key = {
    name: "7D 건조 망고",
    type: "당절임"
}
print(dict_key)

일반적으로 이런 형태로 코드를 사용하는 경우는 거의 없다.
따라서 키를 문자로 사용할 때는 반드시 따옴표를 붙여야 한다.


딕셔너리에 값 추가/제거
딕셔너리에 값을 추가할 때는 키를 기반으로 값을 입력
딕셔너리[새로운키] = 새로운 값


# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임",
    "ingredient": ["망고", "설탕", "메타중아황산나트륨", "치자황색소"],
    "origin": "필리핀"
}

# 출력
print("name:", dictionary["name"])
print("type:", dictionary["type"])
print("ingredient:", dictionary["ingredient"])
print("origin:", dictionary["origin"])
print()

# 값을 변경
dictionary["name"] = "8D 건조 망고"
print("name:", dictionary["name"])

# 값 추가
dictionary["price"] = 5000

print(dictionary)



# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임",
    "ingredient": ["망고", "설탕", "메타중아황산나트륨", "치자황색소"],
    "origin": "필리핀"
}

# # 이미 존재하고 있는 키를 지정하고 값을 넣으면 기존의 값을 새로운 값으로 대치함
# dictionary["name"] = "8D 건조 파인애플"
# print(dictionary)


# 딕셔너리 요소 제거 / 리스트 처럼 del 키워드를 사용해 특정 키를 지정
del dictionary["ingredient"]
print(dictionary)



# 아무것도 없는 딕셔너리에 요소를 추가해 출력는 예제

# 딕셔너리에 요소 추가하기
# 딕셔너리 선언
dictionary = {}

# 요소 추가 전에 내용을 출력해봅니다.
print("요소 추가 이전:", dictionary)

# 딕셔너리에 요소를 추가합니다.
dictionary["name"] = "새로운 이름"
dictionary["head"] = "새로운 정신"
dictionary["body"] = "새로운 몸"

# 출력 합니다.
print("요소 추가 이후:", dictionary)



딕셔너리에 요소 제거하기

# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임"
}

# 요소 제거 전에 내용을 출력
print("요소 제거 이전:", dictionary)

# 딕셔너리의 요소를 제거
del dictionary["name"]
del dictionary["type"]

# 요소 제거 후 내용 출력
print("요소 제거 이후:", dictionary)


KeyError 예외
리스트의 길이를 넘는 인덱스에 접근하면 IndecError가 발생했다.
딕셔너리도 존재하지 않는 키에 접근하면 KeyError가 발생한다.

dictionary = {}
print(dictionary["key"])
del dictionary["key"]

# KeyError: 'key'


# 리스트는 '인덱스'를 기반으로 값을 저장하므로 IndexError
# 딕셔너리는 '키'를 기반으로 값을 저장하므로 KeyError가 발생
# 값을 제거 할 때도 마찬가지


# 딕셔너리 내부에 키가 있는지 확인하기

# in 키워드
# 키가 존재하는지 확인하고 값에 접근하기

# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임",
    "ingredient": ["망고", "설탕", "메타중아황산나트륨", "치자황색소"],
    "origin": "필리핀"
}

# 사용자로부터 입력받기
key = input("> 접근하고자 하는 키:")

# 출력
if key in dictionary:
    print(dictionary[key])
else:
    print("존재하지 않는 키에 접근하고 있습니다.")


# get() 함수
# 존재하지 않는 키에 접근하는 상황에 대한 두 번째 대처 방법
# get() 함수는 딕셔너리의 키로 값을 추출하는 기능으로 
# 딕셔너리[키]를 입력할 때와 같은 기능을 수행하지만 
# 존재하지 않는 키에 접근할 경우 KeyError를 발생시키지 않고 None을 출력함

# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임",
    "ingredient": ["망고", "설탕", "메타중아황산나트륨", "치자황색소"],
    "origin": "필리핀"
}

# 존재하지 않는 키에 접근
value = dictionary.get("존재하지 않는 키")
print("값:", value)

# None 확인 방법
if value == None:
    print("존재하지 않는 키에 접근했었습니다.")


for 반복문 : 딕셔너리와 함께 사용하기
for 키 변수 in 딕셔너리:
    코드

# 딕셔너리 선언
dictionary = {
    "name": "7D 건조 망고",
    "type": "당절임",
    "ingredient": ["망고", "설탕", "메타중아황산나트륨", "치자황색소"],
    "origin": "필리핀"
}

# for 반복문 사용
for key in dictionary:
    # 출력
    print(key, ":", dictionary[key])


마무리_171p

# 1
dict_a = {}
dict_a['name:'] = '구름'
print(dict_a)
del dict_a['name:']
print(dict_a)

# 2_빈칸에 반복문과 print() 함수를 조합하시오
pets = [
    {"name": "구름", "age": 5},
    {"name": "초코", "age": 3},
    {"name": "아지", "age": 1},
    {"name": "호랑이", "age": 1}
]
print("# 우리 동네 애완 동물들")
빈칸

실행결과
우리 동네 애완 동물들
구름 5살
초코 3살
아지 1살
호랑이 1살


for pet in pets:
    print(pet["name"], str(pet["age"])+"살" )


# 3_numbers 내부에 들어 있는 숫자가 몇 번 등장하는지 출력하는 코드

# 숫자는 무작위로 입력해도 상관없습니다.
numbers = [1, 2, 6, 8, 4, 3, 2, 1, 9, 5, 4, 9, 7, 2, 1, 2, 5, 4, 2, 2, 4, 6, 6, 2]
counter = {}

for number in numbers:
    if number in counter:
        counter[number] = counter[number] + 1
    else:
        counter[number] = 1


# 최종출력
print(counter)


4
파이썬은 다음과 같은 방법으로 특정 값이 어떤 자료형인지 확인 할 수 있다.
print(type("문자열") is str)
print(type([]) is list)
print(type({}) is dict)

# 실행결과


# 딕셔너리 선언
character = {
    "name": "기사",
    "level": 12,
    "items": {
        "sword": "불꽃의 검",
        "armor": "풀플레이트"
    },
    "skill": ["베기", "세게 베기", "아주 세게 베게"]
}

# for 반복문 사용
for key in character:
    if type(character[key]) is dict:
        for small_key in character[key]:
            print(small_key, ":", character[key][small_key])
    elif type(character[key]) is list:
        for item in character[key]:
            print(key, ":", item)
    else:
        print(key, ":", character[key])