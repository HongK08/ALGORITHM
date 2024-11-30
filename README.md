# ALGORITHM FOR PYTHON


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
            res.append(i)        # res.append(i) 를 통해서 찿은 i값을 반환이 아닌 res 리스트에 저장을 해준다
    return res                   # 그리고 그 res 를 반환해주면 해당 값이 몇번에 있는지 LIST 형태로 반환이 된다
    v = [10,23,11,35,21,17,23,15,8]
    print(src_list_all(v , 23)

    
