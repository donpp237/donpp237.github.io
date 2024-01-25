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

### 주의

Debug 빌드로 테스트했을 경우 Target이 Null로 변경되지 않을 수 있기 때문에
Release 빌드 테스트까지 확인해봐야한다.
