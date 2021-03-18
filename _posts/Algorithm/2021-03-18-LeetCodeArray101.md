---
layout: post
title:  "리트코드 Array101 - Chapter 6"
date:   2021-03-18 07:45:00 +9000
category: [ 알고리즘 ]
tags: [ 알고리즘, LeetCode ]
---

<br>

## **문제**
정렬된 정수 배열이 입력될 때 각 요소들의 제곱을 정렬해보세요. (O(n) 솔루션이 존재함)

### 예시
```
input: [-2, -1, 2, 9]
output: [1, 4, 4, 81]
```
<br>

---

<br>

## **접근 과정**
1. 가장 간단한 해결책은 전체 배열 요소를 제곱하고 다시 정렬하는 방법이다. 전체를 제곱하는데 O(N) 일반적인 정렬의 시간 복잡도가 O(NlogN)이므로 O(N + NlogN)의 시간복잡도를 가진다. 하지만 입력된 배열이 이미 정렬되어있다는 특성을 이용하면 추가로 정렬하지 않고도 O(N) 시간 복잡도로 문제를 해결할 수 있다.

2. 기존 배열과 동일한 크기의 배열을 만들고 맨 뒤(가장 큰 수)부터 채워나간다. 새로운 배열의 맨 뒤에 들어갈 후보는 입력된 배열의 양 끝에 위치한 수 중 하나일 것이다. 양 끝 요소에 포인터를 두고 절대값이 큰 수 부터 새로운 배열의 뒷부분에 차례로 채워넣다보면 문제를 O(N) 시간에 해결할 수 있다. 투포인터 알고리즘 문제이다.

<br>

## **소스 코드**

```c++
class Solution {
public:
    vector<int> sortedSquares(vector<int>& nums) {
        vector<int> result(nums.size());
        
        int l = 0;
        int r = nums.size() - 1;
        int offset = nums.size() - 1;
        
        while (l <= r) {
            if (abs(nums[l]) <= abs(nums[r])) {
                result[offset] = nums[r] * nums[r];
                --r;
            } else {
                result[offset] = nums[l] * nums[l];
                ++l;
            }
            --offset;
        }
        return result;
    }
};
```