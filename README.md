# Week 4 Assignment

## 1. Repository Link
https://github.com/arongrongi/SWE_2021_41_2024_2_week_4
   
## 2. Problem Statement : Write an algorithm to determine if a number `n` is happy.
A **happy number** is a number defined by the following process:
- Starting with any positive integer, replace the number by the sum of the squares of its digits.
- Repeat the process until the number equals 1 (which makes it a happy number) or it enters an endless loop without reaching 1.

Numbers that end in 1 are happy. If the process loops endlessly in a cycle that does not include 1, the number is not happy.

Return **True** if `n` is a happy number, and **False** otherwise.

## 3. Code Description
### 1) Code

```python
def isHappy(n):

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
```

### 2) Description

1. Handle exceptional cases (1 or 7) and return False for non-happy numbers below 10.
2. During `while` loop, Split each digit of the number, square them, and calculate their sum.
3. If the result becomes 1, return **True** as the number is a happy number.
4. If the result is the same as the previous number or meets specific conditions, return **False**.
5. Continue the process by repeating the calculations with the new `n`.

---

# Week 5 Assignment
> ```docker
> docker exec ossp-container cat /etc/os-release
> ```
> > This command executes the `cat /etc/os-release` command inside the running container named **ossp-container**.
> > \
> > The `/etc/os-release` file contains operating system identification data, so this command is used to retrieve information about the OS running inside the container, such as its name, version, and other details.
> > \
> > Output
> > \
> > <img src= "

> ```docker
> docker exec ossp-container git --version
> ```
> > This command runs `git --version` inside the ossp-container to **check the installed version of Git in that container**.
> > \
> > It helps confirm whether Git is installed and which version is running in the container.

> ```docker
> docker exec ossp-container python3 --version
> ```
> > This command executes `python3 --version` inside the container named ossp-container to **check the version of Python 3 installed in the container**.
> > \
> > It outputs the Python 3 version number.

> ```docker
> docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
> ```
> > This command **inspects the Docker container ossp-container** and **extracts information about the bind mounts** (file or directory bindings between the host and the container).
> > \
> > The `--format="{{ .HostConfig.Binds }}"` part formats the output to **specifically display the bind mount configurations**, which show how directories on the host machine are mapped to the container.
