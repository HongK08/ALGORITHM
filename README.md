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
            res.append(i)        # res.append(i) 를 통해서 찿은 i값을 반환이 아닌 res 리스트에 저장을 해준다
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
