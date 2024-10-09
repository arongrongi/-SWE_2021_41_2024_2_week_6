# Week 4 Assignment
\
### Repository Link
> [GITHUB LINK] https://github.com/arongrongi/SWE_2021_41_2024_2_week_4
\
### Code
> def isHappy(n):

  if(n == 1 or n == 7): # 예외 case 처리
    return True
  if(n < 10):
    return False

  while(True):

    arr = []
    result = 0

    for i in str(n): # 입력받은 숫자 n을 앞에서부터 분리 & 제곱해서 arr에 저장
      arr.append(int(i) ** 2)

    result = sum(arr) # arr 내부 숫자들 합 구하기
    #print("result: " + result1 + "\n")

    if(result == 1):
      return True
    if(result == n or result < 10 and result != 7): # 무한 루프 방지
      return False

    n = result # n을 sum으로 초기화, 다시 루프 진행

def main():
  num = int(input())
  result = isHappy(num)

  if(result): print("True")
  else: print("False")

if __name__ == "__main__":
  main()
