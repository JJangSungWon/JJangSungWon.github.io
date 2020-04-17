---
layout: post
title: "[BOJ] 14888 연산자 끼워넣기"
date: 2020-04-13
author : 장성원
categories : 백준
---

# 연산자 끼워넣기

[문제링크](https://www.acmicpc.net/problem/14888)

<br>

## 문제 요약

- Brute Force
- DFS

<br>

## 아이디어

가지고 있는 연산자를 활용할 수 있는 **모든 경우의 수를 대입**하면 된다.    
문제를 풀면서 2가지만 주의하면 된다.    

1. 음수를 양수로 나누는 경우는 음수를 양수로 바꾼 뒤 몫을 취하고, 그 몫을 음수로 바꿔서 구한다.  
2. 최댓값, 최솟값의 범위가 -10억보다 크거나 같고, 10억보다 작거나 같기 때문에 초기화에 신경 써야 한다.  최댓값을 -1로 초기화하면 틀렸습니다가 나온다.

<br>

## 코드

```python
import sys


def DFS(cnt, value, operation):
    global max_val, min_val

    if cnt == N:
        max_val = max(max_val, value)
        min_val = min(min_val, value)
        return

    for i in range(4):
        if operation[i] != 0:
            operation[i] -= 1
            if i == 0:  # +
                DFS(cnt + 1, value + data[cnt], operation)
            elif i == 1:  # -
                DFS(cnt + 1, value - data[cnt], operation)
            elif i == 2:  # *
                DFS(cnt + 1, value * data[cnt], operation)
            elif i == 3:  # /
                if value < 0:
                    DFS(cnt + 1, -(-value // data[cnt]), operation)
                else:
                    DFS(cnt + 1, value // data[cnt], operation)
            operation[i] += 1


if __name__ == "__main__":
    # input
    N = int(input())
    data = list(map(int, input().split()))
    operation = list(map(int, input().split()))

    max_val = -pow(10, 11)
    min_val = sys.maxsize

    DFS(1, data[0], operation)

    # print
    print(max_val)
    print(min_val)

```

<br>

## 정리

초깃값을 설정할 때 결과의 범위를 참고해야 한다는 점을 깨달았다. 문제는 완전 탐색으로 구현해도 시간 초과가 발생하지 않아 큰 어려움 없이 풀 수 있었다.

 <br>

읽기 불편하거나, 틀린 점이 있다면 알려주시면 감사하겠습니다!

읽어주셔서 감사합니다.