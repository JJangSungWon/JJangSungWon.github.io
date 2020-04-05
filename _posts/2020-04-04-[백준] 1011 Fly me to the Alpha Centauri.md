---
layout: post
title: "[BOJ] 1011 Fly me to the Alpha Centauri"
date: 2020-04-04
author : 장성원
categories : 백준

---

# Fly me to the Alpha Centauri

[문제링크](https://www.acmicpc.net/problem/1011)

<br>

## 문제 요약

- 규칙

<br>

## 아이디어

y-x의 계산 결과, 즉 거리에 따른 규칙성을 찾고자 하였다.

![1011](/assets/image/1011.JPG)

위 그림과 같이 거리 13까지 계산해보니 이동 횟수가 1 증가할 때마다 일정한 규칙이 있음을 발견하였다.

<br>

## 코드

```python
if __name__ == "__main__":

    T = int(input())

    for _ in range(T):
        x, y = map(int, input().split())
        sub = y - x

        init, val, cnt = 3, 2, 3
        flag = 1

        if sub <= 2:
            print(sub)
        else:
            while flag:
                for _ in range(2):
                    if init <= sub < init + val:
                        flag = 0
                        print(cnt)
                        break
                    else:
                        init += val
                        cnt += 1
                val += 1
```

<br>

## 정리

처음에는 그리디 방식으로 접근하였다. 이동할 수 있는 거리 중에서 제일 긴 거리를 이동하면 최소한의 횟수로 도착지에 도달할 수 있다고 생각하였다. 하지만 제일 마지막에 1칸을 이동해야 하는 규칙 때문에 무한정으로 긴 거리를 이동하면 결국 멈출 수 없는 상태가 된다. 

<br>

모든 문제를 특정한 알고리즘을 활용하여 풀고자 하였는데 이번 문제를 풀면서 규칙성을 이용하는 것만으로도 빠르게 구현할 수 있음을 깨달았다.



 <br>

읽기 불편하거나, 틀린 점이 있다면 알려주시면 감사하겠습니다!

읽어주셔서 감사합니다.