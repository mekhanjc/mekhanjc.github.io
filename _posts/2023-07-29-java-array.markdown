---
layout: post
title:  Java 기초 - 배열
date:   2023-07-29 19:31:29 +0900
categories: Java
---
### **배열**

-   배열은 같은 종류의 데이터를 저장하기 위한 자료구조로, (참조형) 객체로 취급된다.
-   배열의 요소를 참조하려면, 0부터 시작하는 index 번호로 각 요소에 접근해야 한다.
-   배열이름.length 속성을 통해 배열의 길이를 조회 가능하다.
-   생성된 당시의 크기로 고정되어 있어, 길이 변경 팔요하다면 새로운 배열을 생성 후 내용을 옮겨야 한다.

<br>
1차원 배열은 다음과 같이 선언할 수 있다.

```javascript
int[] arr1 = int[]; // 배열 생성(각 값은 자료형의 초기값이 들어감)
char arr2[] =  new char[] {'a', 'b', 'c'}; // 배열 생성 및 값 초기화
String[] arr3 = {"apple"}; // 선언과 동시에 초기화

int[] arrCopy = Arrays.copyOf(arr2, 2); // {'a', 'b'}로 두번째 배열 복사
```
<br>
배열을 순회하며 출력하는 방법은 다음과 같다.

```javascript
int arr [] = {1,2,3,4,5};

// 첫번째 순회 방법
for (int i = 0; i < arr.length, ++i){
	System.out.println(arr[i]);
}

// 두번째 순회 방법
for (int x : arr) {
System.out.println( x );
}

// 다음과 같이 출력하면 [1, 2, 3, 4, 5]가 나온다.
System.out.println( Arrays.toString( arr ) );
```
<br>
2차원 이상의 배열은 다음과 같이 선언 가능하다.

다차원 배열은 하위 배열의 주소 참조를 가지므로, 직사각형처럼 크기가 같을 필요가 없으며 멀티탭처럼 연결했다고 생각하면 된다.

```javascript
int[][] arr = new int[10][10];
int arr2[][] = { {1, 2}, 3 };

int[] arr3[] = new int[2][];
arr3[0] = new int[10];
arr3[1] = new int[100];
arr[9][99] = 999;
```
