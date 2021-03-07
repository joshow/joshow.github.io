---
layout: post
title:  "알고스팟 - JUMPGAME"
date:   2021-03-07 07:45:00 +9000
category: [ 알고리즘 ]
tags: [ 알고리즘, 백준 ]
---

[문제 링크](https://www.algospot.com/judge/problem/read/JUMPGAME)
> 알고리즘 문제해결 전략 수록 문제

> 문제 해설이 아닌 풀이하면서 거쳐간 생각들을 기록하는 글입니다.

---

<br>

## **접근 과정**
이 문제는 알고리즘 문제해결 전략 책에서 다이나믹 프로그래밍에 대한 예시로 나오는 문제이다. 책에서는 재귀호출을 통해 완전탐색을 구현한 뒤 메모이제이션을 적용하는데 개인적으로 재귀호출은 익숙한 방법이니 반복문을 통해 구현해보고자 하였다. 재귀호출의 매개변수들을 스택 메모리에 쌓아가듯 벡터 스택에 이동 좌표를 쌓는 방식으로 탐색을 했다... 했는데 하고보니 메모이제이션은 사라지고 DFS와 비슷한 느낌으로 구현되었다. 실제로 책에서도 그래프를 통해 모델링을 할 수 있다고 나와있었다.
아마 문제가 맨 끝에 도달 여부가 아닌 최소 거리를 구하는 문제였다면 DP가 반드시 필요한 문제가 아니었을까 싶다.

<br>

## **소스 코드**

```c++
#include <iostream>
#include <vector>

struct point_t {
    int x;
    int y;
};

bool isValidPoint(point_t p, int n) {
    return p.x < n && p.y < n;
}

const char* jumpGame() {
    int n;
    int board[100][100];

    std::cin >> n;
    for (int y = 0; y < n; ++y) {
        for (int x = 0; x < n; ++x) {
            std::cin >> board[y][x];
        }
    }

    bool canReach = false;
    bool bVisited[100][100] = {
        {false, },
    };
    static std::vector<point_t> stack;
    stack.clear();
    
    stack.push_back({0, 0});
    while (!stack.empty()) {
        int x = stack.back().x;
        int y = stack.back().y;
        stack.pop_back();

        if (bVisited[y][x]) {
            continue;
        }
        bVisited[y][x] = true;

        if (x == n - 1 && y == n - 1) {
            canReach = true;
            break;
        }

        point_t nextPoint = {x + board[y][x], y};
        if (isValidPoint(nextPoint, n)) {
            stack.push_back(nextPoint);
        }

        nextPoint.x = x;
        nextPoint.y = y + board[y][x];
        if (isValidPoint(nextPoint, n)) {
            stack.push_back(nextPoint);
        }
    }
    
    if (canReach) {
        return "YES";
    } else {
        return "NO";
    }
}

int main() {
    std::ios_base::sync_with_stdio(false); std::cin.tie(nullptr);
    int t;
    std::cin >> t;
    for (int test = 0; test < t; ++test) {
        std::cout << jumpGame() << '\n';
    }
    return 0;
}
```