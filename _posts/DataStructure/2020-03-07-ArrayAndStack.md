---
layout: post
title:  "배열과 스택"
date:   2020-03-07 14:00:01 +9000
category: [ 자료구조 ]
tags: [ 자료구조, C언어 ]
---

C코드로 작성한 왼쪽 정렬된 배열과 스택이다.
표준은 C89에 맞추다 그냥 C99에 맞췄다.(stdbool.h는 안썼지만)
자세한 내용은 추후 업데이트 예정

### 배열
```c
#include <limits.h>

#define MAX_ARR_SIZE (10)

#define TRUE (1)
#define FALSE (0)

static int array[MAX_ARR_SIZE];
static size_t count = 0;

int insert_at(size_t index, int n)
{
    size_t i;
    
    if (index > count || count >= MAX_ARR_SIZE)
        return FALSE;
    
    for (i = count; i > index; i--)
        array[i] = array[i - 1];
        
    array[index] = n;
    count++;
    return TRUE;
}

int remove_at(size_t index)
{
    size_t i;
    
    if (index >= count)
        return FALSE;
    
    for (i = index + 1; i < count; i++)
        array[i - 1] = array[i];
    
    count--;
    return TRUE;
}

int get_value(size_t index)
{
    if (index >= count)
        return INT_MAX; // Cannot compile in C89.
    
    return array[index];
}

size_t get_array_count()
{
    return count;
}

size_t get_index_of(int n)
{
    size_t i;
    
    for (i = 0; i < count; i++) {
        if (array[i] == n)
            return i;
    }
    
    return -1;
}
```


<br>

### 스택
```c
#include <limits.h>

#define MAX_STACK_SIZE (20)

#define TRUE (1)
#define FALSE (0)

static int stack_arr[MAX_STACK_SIZE];
static size_t count = 0;

int push(int n)
{
    if (count >= MAX_STACK_SIZE)
        return FALSE;
    
    stack_arr[count++] = n;
    
    return TRUE;
}

int pop()
{
    if (count == 0)
        return INT_MAX;
    
    return stack_arr[--count];
}

size_t get_stack_count()
{
    return count;
}

int search(int n)
{
    int reversed_stack[MAX_STACK_SIZE];
    size_t r_stack_count = 0;
    int result = FALSE;
    
    while (count != 0) {
        reversed_stack[r_stack_count] = pop();
        if (reversed_stack[r_stack_count++] == n) {
            result = TRUE;
            break;
        }
    }
    
    while (r_stack_count != 0)
        push(reversed_stack[--r_stack_count]);
    
    return result;
}
```