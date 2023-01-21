# filter

흐림, 색상변형, 그래픽 효과 를 요소에 적용
보통, 이미지, 배경, 테두리 렌더링을 조정하는데 쓰인다.

CSS 표준은 미리 정의된 효과를 내는 몇 가지 함수를 포함함
SVG필터 요소를 가리키는 URL 참조를 사용하여 SVG 필터를 적용할 수 도 있음

Demo
- filter: blur(5px)
- filter: contrast(200%)(대조? 뚜렷한?)
- filter: grayscale(80%)(흑백으로 출력된)
- filter: hue-rotate(90deg)(색조의??)
- filter: drop-shadow(16px 16px 20px red) invert(75%)

## Syntax
```css
*{
  /* SVG 필터를 가리키는 URL */
  filter: url("filters.svg#filter-id");

  /* <filter-cuntion> 값 */
  filter: blur(5px);
  filter: brightness(0.4);
  filter: contrast(200%);
  filter: drop-shadow(16px 16px 20px blue);
  filter: grayscale(50%);
  filter: hue-rotate(90deg);
  filter: invert(75%);
  filter: opacity(25%);
  filter: saturate(30%);
  filter: sepia(60%);

  /* 다중 값 */
  filter: contrast(175%) brightness(3%);

  /* 필터 없음 */
  filter: none;

  /* Global Values */
  filter: inherit;
  filter: initial;
  filter: unset;
}
```

함수를 사용한다면 다음 문법을 사용하세요
```
filter: <filter-function> [<filter-function>]* | none
```

SVG<filter> 요소에 대한 참조를 사용하려면 다음 구문을 사용하세요
```
filter: url(svg-url#element-id)
```

## 보간
보간의 처음과 끝 필터의 함수 목록 길이가 같고ㅡ 그 안에 <url> 값이 없으면, 각 필터 함수를 스스로의 특정 규칙을 따라 고반됩니다.
함수의 길이가 서로 다를 때는 긴 필터목록에만 존재하는 필터를 짧은 필터 목록에 추가하며, 이 때 추가된 필터의 값으로는 누락 값 (누락 시 기본값)을 사용합니다.
이후 각 필터가 `none`일 경우 다른 쪽 필터 목록을 모두 가져오고, 각각에 누락 값을 대입한 후 보간합니다.
이 외의 경우에는 이산적 보간을 사용합니다.

## 함수
`filter` 속성은 `none` 또는 아래의 함수를 하나 이상 ㅎ사용해 지정할 수 있습니다.
어떤 함수의 매개변수가 유효하지 않다면, 그 함수는 none을 반환합니다.
따로 명시하지 않으면 백분율 값을 받는 함수는 그 백분율의 소수 표기도 받을 수 있습니다.

## SVG 필터
### url()
SVG필터를 가리키는 URI를 받습니다. 외부 XML 파일에 포함된 필터도 가능합니다.
```
filter: url(resources.svg#c1)
```

## 필터 함수
### `blur()`
`blur()` 함수는 주어지 이미지에 가우시안 블러를 적용합니다.
radius값은 정규 분포의 표준 편자, 즉 화면에서 혼합할 픽셀의 수를 지정하므로 값이 클수로 이미지가 흐려집니다.
보간 시 누락값은 0입니다.
매개변수는 CSS길이로 변시되어있지만, 백분율 값은 받지 않습니다.
```
filter: blur(5px)
```

### `brightness()`
주어진 이미지에 선형 배수를 적용하여 이미지를 밝거나 어둡게 표시
`0%`-> 완전 검으색
`100%`-> 원래 이미지 그보다 큰 값도 가능
보간 시 누락값은 1입니다.

### `contrast()`
주어진 이미지의 대비를 조정합니다.
`0%`일 경우 환전히 회색 이미지가 되고, 
`100%`는 원래 그대로
`100% 이상`은 대비가 더 큰 이미지가 생성
보간 시 누락값은 1입니다.

### `drop-shadow()`
주어진 이미지에 그림자 효과를 적용합니다.
추가하는 그림자는 주어진 이미지의 알파 마스크에 특정한 색상과 오프셋, 흐림 효과를 적용하고 이미지 밑에 함성한 것입니다.

이 함수는 `Inset` 키워드를 제외하고 (CSS3 Backgrounds에 정의된)`<shadow>`자료형의 매개변수를 그대로 받을 수 있습니다.
box-shadow와 속성이 비슷하지만, 일부 브라우저에서는 필터를 사용했을 때, 성능 향상을 위해 하드웨거 가속을 사용한다는 차이점이 있습니다.