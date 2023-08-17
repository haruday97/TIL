# Flexbox

## Flexbox란
다른 크기의 화면에서 HTML 요소들을 자동으로 재정렬해주어 웹 페이지의 레이아웃을 일관적으로 해주는 레이아웃 모델이다.  
페이지의 콘텐츠 상자안에 아이템을 배치하는 데에 쓰인다.  
속성들의 종류는 다음과 같다.  
<ul>
    <li>display</li>
    <li>flex-direction</li>
    <li>justify-content</li>
    <li>align-items</li>
    <li>flex-wrap</li>
    <li>flex-flow</li>
    <li>align-content</li>
    <li>order</li>
    <li>align-self</li>
    <li>flex</li>
</ul>

## 주축과 교차축
![flexbox_axes](../Assets/flexbox_axes.png)  
주축(Main axis)과 교차축(Cross Axis)은 Flexbox의 핵심 개념이다.  
주축은 `flex-direction` 속성을 사용하여 지정하며 교차축은 이에 수직인 축으로 결정이 된다.  
그냥 가로면 주축, 세로면 교차축이 아니다.

## flex-direction
주축의 디폴트 방향은 왼쪽에서 오른쪽이다.  
이는 flex-direction 속성을 사용해 바꿀수있다.
<ul>
    <li> row </li>
    left to right, default 
    <li> row-reverse </li>
    right to left
    <li> column </li>
    top to bottom
    <li> column-reverse </li>
    bottom to top
</ul>

## justify-content
주축을 기준으로 아이템을 어떻게 정렬할지 결정하는 속성이다.
<ul>
    <li> flex-start </li>
    왼쪽정렬, default 
    <li> center </li>
    중앙정렬
    <li> flex-end </li>
    오른쪽정렬
    <li> space-between </li>
    요소 사이에 간격을 띄운다.
    <li> space-around </li>
    요소 둘레에 간격을 띄운다.
    <li> space-evenly </li>
    요소와 요소 사이, 요소와 컨테이너 사이에도 동일한 간격을 띄운다.
</ul>

## flex-wrap
더 이상의 여유공간이 없을때 요소의 위치를 다음 줄로 넘겨줄지를 결정하는 속성이다.
<ul>
    <li>nowrap</li>
    요소가 다음줄로 넘겨지지 않는다, default
    <li>wrap</li>
    요소가 다음줄로 넘어간다.
    <li>wrap-reverse</li>
    요소가 다음줄로 넘어가며 교차축의 방향이 바뀐다.
</ul>

## align-items
교차축을 기준으로 아이템을 어떻게 정렬할지 결정하는 속성이다.  
<ul>
    <li> stretch </li>
    요소의 높이를 컨테이너의 높이와 같게 지정한후 정렬, default
    <li> flex-start </li>
    위쪽정렬, default 
    <li> center </li>
    중앙정렬
    <li> flex-end </li>
    아래쪽정렬
    <li> baseline </li>
    요소를 컨테이너의 기준선을 기준으로 정렬한다.
</ul>

## align-content
flex-wrap 속성의 동작을 변경해 여러 row나 column을 정렬한다.
수직이 주축일 경우 열 사이의 공간을 조정하며, 수평이 주축일 경우 행 사이의 공간을 조정한다.
wrap이나 wrap-reverse가 적용되지 않았다면 아무런 동작을 수행하지않는다.  

<ul>
    <li> stretch </li>
    default
    <li> flex-start </li>
    <li> center </li>
    <li> flex-end </li>
    <li> space-between </li>
    <li> space-around </li>
</ul>

## References
https://developer.mozilla.org/ko/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox
http://www.tcpschool.com/css/css3_expand_flexbox