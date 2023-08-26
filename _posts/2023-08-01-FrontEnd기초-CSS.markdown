---
layout: post
title:  FrontEnd 기초 - CSS
date:   2023-08-01 19:31:29 +0900
categories: Front-End
---
### Cascading Style Sheets

 HTML 문서를 화면에 표시하는 방식을 정의한 언어로, 웹 문서의 내용과 관계없이 디자인만 바꿀 수 있다. 다양한 기기에 맞게 반응형으로 바뀌는 문서를 만들 수 있다.

-   외부 스타일 시트 : <head> 안에 <link rel="stylesheet" href="\[.css 파일 경로\]">를 작성한다.
-   내부 스타일 시트 :  <style> 태그 사이에 css 규칙을 작성한다. 외부 스타일 시트보다 우선 적용된다.
-   인라인 스타일 : tag에서 style 속성을 사용하고 속성값으로 css 규칙을 작성한다. 내부 스타일 시트보다 우선 적용된다.

###  CSS selector

  HTML 문서에서 CSS 규칙을 적용할 요소를 정의한다. 기본선택자, 그룹선택자, 결합자, 의사클래스/요소로 나뉜다.

-   Universal selector (전체 선택자) : HTML 문서 내 모든 element를 선택한다. \* { style properties } 형식이다.
-   Type selector (유형 선택자) : 태그명을 이용하여 스타일을 적용할 태그를 선택한다. element { style properties } 형식
-   Class selector (클래스 선택자) : class가 적용된 모든 태그를 선택한다. .class-name { style properties } 형식
-   ID selector (ID 선택자) : id 특성 값을 비교하여, 동일한 id를 가진 태그를 선택한다. #id-value { style properties } 형식
-   Selector list (선택자 목록) : ,(comma)를 이용하여 선택자 그룹을 생성한다. element, element { style properties } 형식  
    
-   Descendant combinator (자손 결합자) : 첫번째 요소의 자손인 노드를 선택한다. selector1 selector2 { style properties } 형식
-   Child combinator (자식 결합자) : 첫 번째 요소의 바로 아래 자식인 노드를 선택한다. selector1 > selector2 { style properties } 형식
-   General sibling combinator (일반 형제 결합자) : 첫 번째 요소를 뒤따르면서 같은 부모를 공유하는 두 번째 요소를 모두 선택한다. former-element ~ target-element { style properties } 형식  
    
-   Adjacent sibling combinator (인접 형제 결합자) : 첫 번째 요소의 바로 뒤에 위치하면서 같은 부모를 공유하는 두번째 요소 선택한다. former-element + target-element { style properties } 형식

만약 같은 요소에 2개 이상의 CSS 규칙이 적용된 경우, !important 가 우선 적용되고, 그 다음은 구체적인 규칙, 그리고 마지막 규칙이 차례로 우선 적용된다.

#### Inheritance

부모 요소에 적용된 스타일은 자식 요소에게 상속이 되는 속성이 있고, 아닌 속성이 있다. 상속되는 속성으로 대표적인 것은 color가 있다. 반대로, 상속되지 않는 속성의 대표적인 예는 border이다. 사용 시 주의해서 결과를 확인하자.

### CSS 속성

 크기 단위의 길이 값으로는 px, cm, mm, in, em, rem 등이 있다. em은 부모의 글자 크기를 기준으로 배율을 잡는 것이고, rem은 문서의 루트에 있는 글자 크기(일반적으로 16px)를 기준으로 배율을 잡는다. 그 외에 상위 블록에 대한 백분율 단위를 쓰거나 auto로 설정할 수 있다.

 색상 단위는 red, blue 등의 키워드를 사용하거나, 16진수 표기법 혹은 함수형 표기법을 사용하는 RGB색상, 그리고 색상과 채도, 명도를 통해 특정 색을 표현하는 HSL 색상을 사용하여 나타낼 수 있다.

#### Font

-   font-family : 글꼴 지정 (font name).
-   font-size : 글자 크기 지정.
-   font-style : 글자 스타일 지정.
-   font-variant : 소문자를 작은 대문자(small-caps)로 변형.
-   font-weight : 글자 굵기 지정.
-   font : font에 관한 속성을 한번에 지정하는 단축형(short hand) 속성

#### Text

-   text-align : text 정렬 방식 지정
-   text-decoration : text 장식 지정.
-   text-indent : Text-block 첫 라인의 들여쓰기 지정.
-   text-transform : text 대문자화.
-   white-space : element 안의 공백 지정.
-   vertical-align : 수직 정렬 지정.
-   letter-spacing : 문자 간의 space 간격을 줄이거나 늘림.
-   word-spacing : 단어 간의 간격 지정.
-   line-height : 줄(행) 간격 지정.
-   color text : 색상 지정

#### background

-   background-color : 배경색을 지정.
-   background-image : 배경을 이미지로 지정.
-   background-attachment : 배경 이미지를 고정하거나 scroll여부를 지정.
-   background-repeat : 배경 그림의 반복 여부를 지정.
-   background-position : 배경 그림의 위치를 지정.
-   background : 배경 관련 속성을 한번에 지정.(font 속성과 달리 속성 값 순서에 구애 받지 않음.)
-   background-size : 배경 이미지 크기 조절
-   background-clip : 배경 적용 범위 조절

#### Box model

-   margin 속성은  box의 외부 둘레의 너비를 지정한다.  
    값이 1개일 경우 모든 면에 적용  
    2개일 경우 {위 아래}, {오른쪽 왼쪽}  
    3개의 경우 {top} {right left} {bottom}  
    4개이면 top, right, bottom, left 순으로 적용된다.  
    0 auto를 통해 가운데 정렬이 되도록 설정 가능하다.  
    margin끼리는 다른 box의 경계면인 border에 닿을 때까지 서로 상쇄되는 마진상쇄 현상이 일어날 수 있다.
-   padding 속성은 box의 내부 둘레의 너비를 지정한다. 값 적용 순서는 margin과 같다.
-   border는 box의 테두리로, 다음과 같은 키워드로 속성을 지정할 수 있다.  
    border-style : 선의 모양  
    border-width : 선이 굵기  
    border-color : 선의 색상  
    border-radius : 선의 모서리를 둥글게 만드는 속성  
    box-shadow : 그림자 효과

#### display

  display는 줄 바꿈이 일어나는 요소인 block과 linline으로 나눌 수 있다. block은 화면 전체의 가로 폭을 차지하며, block 레벨의 요소 안에는 inline 레벨 요소가 들어갈 수 있다. inline 요소는 줄 바꿈이 일어나지 않는, 행의 일부가 되는 요소로 content 너비만큼 가로 폭을 차지한다. width, height, margin-top, margin-bottom을 지정할 수 없어서 상하 여백은 line-height로 지정한다. inline-blick요소는 앞의 두 레벨 요소의 특징을 모두 갖는다. inline처럼 한줄에 표시 가능하고 width, height, margin 속성을 지정 가능하다. 마지막으로 display:none은 해당 요소를 화면에 표시하지 않는데, visibility:hidden과는 다르게 공간마저도 차지하지 않는다.

#### position

-   static(기본) : 상단, 좌측에서의 거리를 지정할 수 없다.
-   relative : top, left 거리를 지정할 수 있다.
-   absolute : 자신의 상위 box속에서의 top, left, right, bottom 등의 절대적인 위치를 지정한다.
-   fixed : 스크롤(scroll)이 일어나도 항상 화면상의 지정된 위치에 있다.

이 외에 float와 clear를 사용하여 박스 위치 배치와 속성 값 취소가 가능하다.

### Flexbox

Flexible box module은 인터페이스 내의 아이템들 간의 공간 배분과 정렬 기능을 제공하기 위한 1차원 레이아웃 모델로 설계되었다. display 속성을 이용하여 flex container를 생성할 수 있다.

  ▪ flex-direction : container 안의 item들의 나열되는 방향 (행/렬)  
  ▪ flex-wrap : container 안의 item들의 크기가 container의 크기 보다 클 때 줄 넘김 (2줄 이상이 됨)  
  ▪ flex-flow : 방향과 줄 넘김을 동시에 설정 (flex-direction + flex-wrap)  
  ▪ justify-content : 메인축의 정렬을 제어 (일렬로 선 방향의 시작점/끝점/간격)  
  ▪ align-items : 교차축의 정렬을 제어 (일렬과 수직인 방향의 시작점/끝점/간격)  
  ▪ align-content : wrap 속성에 의해서 여러 줄이 발생한 경우의 교차축 정렬

[CSS Flexbox Container (w3schools.com)](https://www.w3schools.com/css/css3_flexbox_container.asp) 에서 적절한 예시를  볼 수 있다.

#### Flex Item

  ▪ order : 각 item의 배치 순서 제어 (기본값은 0이고, 음수이면 앞에 온다)  
  ▪ flex-basis : item의 너비를 지정   
  ▪ flex-grow : item의 팽창 제어 (기본값 0, 음수는 불가능)  
  ▪ flex-shrink : item의 수축 제어  (기본값 1, 음수는 불가능)  
  ▪ flex : flex-grow, flex-shrink, flex-basis의 속성을 단축 지정  
  ▪ align-self : 특정 item의 교차 축 정렬(align-content)을 제거