# ALGORITHM FOR PYTHON


#리스트에서 찿는 숫자의 위치를 출력하는 알고리즘

    def src_list(a,x):
    n = len(a)
    for i in range(0,n):
        if x == a[i]:
            return i
    return -1

v = [10,23,11,35,21,17,15,8]
print(src_list(v,11))

