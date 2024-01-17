---
title: "WeakReference"
permalink: /study/
layout: single
---

## 개요

WeakReference Class에 대한 내용 검토

## 용도

메모리에 할당된 불필요한 객체들의 대한
제거를 통해 메모리 Leak 제거

## 대상

항상 메모리에 유지하지 않아도 되는 객체

## 내용

### 생성

```C#
Test test = new Test();
WeakReference refTest = new WeakReference(test);
```

### 활용

```C#
WeakReference refTest = new WeakReference(test);
Test temp = (Test)refTest?.Target;
```
