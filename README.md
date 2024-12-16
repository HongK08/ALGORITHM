# ALGORITHM FOR PYTHON

# 신나는 순차 탐색 놀이
#1 리스트에서 찿는 숫자의 위치를 출력하는 알고리즘

    def src_list(a,x):     # a = 서칭할 리스트를 지정하며  x = 리스트 내의 찿고 싶은 값을 지정한다.
    n = len(a)             # list의 길이를 구해야 하므로 len(a) 를 하며 그 값을 n 이라는 변수에 저장한다.
    
    for i in range(0,n):   # 핵심 반복문이다 즉 list의 0번과 n(아까 구한 리스트의 길이니까 최종 셀 번호가 된다)
        if x == a[i]:      # x값이(찿으려는 값이)  a[i] 와 일치한다면 return i 를 해줌.
            return i
            
    return -1              # 그런데 그 값이 검색되지 않는다면 -1를 반환해준다.
    
    v = [10,23,11,35,21,17,23,15,8]
    print(src_list(v,23))

#2 1번의 알고리즘은 리스트 내 중복 값의 위치 중 제일 좌측의 값만을 출력하는데 그걸 고쳐보자

    def src_list_all(a,x):
    n = len(a)
    res = []                     # 여기서 빈 리스트를 만들어 결과값을 저장하게 될거다.

    for i in range(0,n):
        if x == a[i]:
            res.append(i)        # res.append(i) 를 통해서 찿은 i값을 반환이 아닌 res 리스트에 저장을 해준다 + 값을 여러개를 모아버리면 되겠네
    return res                   # 그리고 그 res 를 반환해주면 해당 값이 몇번에 있는지 LIST 형태로 반환이 된다
    
    v = [10,23,11,35,21,17,23,15,8]
    print(src_list_all(v , 23)

#3 응용 (이름 찿아보기)

    def src_name(st_num,st_name,find_num):        # 학생 번호+학생 이름+그리고 내가 찿을 학생의 번호 를 지정해준다
        n = len(st_num)                           # 내가 서칭할 대상 리스트를 읽는데 우선 학생 번호를 읽는다 (1:1) 로 대응
        for i in range(0, n):
            if find_num == st_num[i]:             # 이제 찿는 번호가 st_num이라는 리스트의 값이랑 일치한다면 마찬가지로 반환해준다
                return st_name[i]
        
        return "?? 없는데요 선생님?"                # 없으면 없다고 하는 착한 학생 만들기
    
    st_num=[1,4,6,3,2]
    st_name=['응애','응애1','응애2','응애3','응애4']
    
    print(src_name(st_num, st_name, 2))

# 선택 정렬
    def selection_sort()

# 버블정렬도 알아둘것.
    1. 가장 작은사람먼저 뺀다
    2. 옆사람과 비교하면서 자리를 바꿔가는 알고리즘임





# 한참 이후의 최대 수익 알고리즘
def max_profit(price):
    n = len(price)
    max_profit = 0
    min_price = price(0)


    for i in range(1,n):
    
        profit = price(i) - min_price
        max_profit = profit
    if price(i) < min_price(i):
        min_price = price(i)
    return max_profit


stock = {10300 : "6/1" , 9800 : "6/2" , 9800 : "6/3" , 8200 : "6/4" , 7800 : "6/5" , 8300 : "6/8" , 9500 : "6/9" , 9800 : "6/10" , 10200 : "6/11" , 9500 : "6/12"}
print(max_profit(stock))

print(f'구매한 가격과 날은 {max_profit}, 입니다.')


# 이거로 for 문 두개를 돌리는 알고리즘과 하나일때의 속도 차이를 확인해보자
## 시간 측정 예제 (알고리즘의 성능 평가를 하게 됨)

# 최대 수익 문제를 푸는 두 알고리즘의 계산 속도 비교하기
# 최대 수익 문제를 O(n*n)과 O(n)으로 푸는 알고리즘을 각각 수행하여
# 걸린 시간을 출력/비교함

 

import time     # 시간 측정을 위한 time 모듈
import random  # 테스트 주가 생성을 위한 random 모듈

 

# 최대 수익: 느린 O(n*n) 알고리즘
def max_profit_slow(prices):
    n = len(prices)
    max_profit = 0
    for i in range(0, n - 1):
        for j in range(i + 1, n):
            profit = prices[j] - prices[i]
            if profit > max_profit:
                max_profit = profit

 

    return max_profit

 

# 최대 수익: 빠른 O(n) 알고리즘
def max_profit_fast(prices):
    n = len(prices)
    max_profit = 0
    min_price = prices[0]
    for i in range(1, n):
        profit = prices[i] - min_price
        if profit > max_profit:
            max_profit = profit
        if prices[i] < min_price:
            min_price = prices[i]

 

    return max_profit

 

def test(n):
    # 테스트 자료 만들기(5000부터 20000까지의 난수를 주가로 사용)
    a = []
    for i in range(0, n):
        a.append(random.randint(5000, 20000))
    # 느린 O(n*n) 알고리즘 테스트
    start = time.time()       # 계산 시작 직전 시각을 기억
    mps = max_profit_slow(a)  # 계산 수행
    end = time.time()         # 계산 시작 직후 시각을 기억
    time_slow = end - start   # 두 시각을 빼면 계산에 걸린 시간
    # 빠른 O(n) 알고리즘 테스트
    start = time.time()       # 계산 시작 직전 시각을 기억
    mpf = max_profit_fast(a)  # 계산 수행
    end = time.time()         # 계산 시작 직후 시각을 기억
    time_fast = end - start   # 두 시각을 빼면 계산에 걸린 시간
    # 결과 출력: 계산 결과
    print(n, mps, mpf)  # 입력 크기, 각각 알고리즘이 계산한 최대 수익 값(같아야 함)
    m = 0  # 느린 알고리즘과 빠른 알고리즘의 수행 시간 비율을 저장할 변수
    if time_fast > 0:  # 컴퓨터 환경에 따라 빠른 알고리즘 시간이 0으로 측정될 수 있음(이럴 때는 0을 출력)
        m = time_slow / time_fast  # 느린 알고리즘 시간 / 빠른 알고리즘 시간
    # 입력 크기, 느린 알고리즘 수행 시간, 빠른 알고리즘 수행 시간, 느린 알고리즘 시간 / 빠른 알고리즘 시간
    # %d는 정수 출력, %.5f는 소수점 다섯 자리까지 출력을 의미
    print("입력크기=%d 느린알고리즘시간=%.5f 빠른알고리즘시간%.5f 시간비율=%.2f" % (n, time_slow, time_fast, m))

 

test(100)
test(10000)
test(30000)
test(50000)
