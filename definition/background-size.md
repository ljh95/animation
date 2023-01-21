## background-size

요소 background image의 사이즈를 설정
이미지 왼쪽을 자연 사이즈, 뻗은, contrained(부자연스러운, 강요된) 이 가능하다.

- background-size: contain; -> 요소(배경)를 계속 넣어서 범위를 꽉 채운다.
- background-size: cover; -> 배경을 늘려서 범위를 꽉 채운다.

영역은 덮여지지 않는다. 배경 이미지
채워진다. bg-color 속성, bg-color는 보인다 뒤에 배경 이미지가 투명성을 보일경우,

contain과 cover를 사용한다.
width만 설정할 경우, height는 auto가 된다.
width, height를 둘다 사용하면, 첫번째가 width, 두번째가 height
각각의 값은 length, percentage, auto를 가질 수 있다.

여러개의 bg-image를 특정하고 싶은 경우, 분리해가 값을 comma를 기준으로

### Values

`contain`, 가능한 이미지를 cropping(불필요한 부분을 다듬기, 잘라내다), stretching하지 않고 bg-repeat: no-repeat오 사용된다. 이미지보다 영역이 큰경우, tiling(타일링, 여러번 붙인다), bg-no-repeat하지 않는이상!
`cover`
`auto`
`<length>`
`<percentage>`
