# pointer-event
는 어떤 상황일 경우, 포인터 이벤트 대상이 될 수 있는지 지정합니다.

## Values
`auto`
- 기본
- SVG 콘텐츠에서는 auto와 visiblePainted가 동일

`none`
- 포인터 이벤트 X
- 하지만 자손이 pointer-event를 지정한 경우,
- 자손은 대상이 될 수 있다.
- 이때는 이벤트 캡처/버블 단계에서 none을 지정한 요소의 이벤트 처리기를 발동할 수 있습니다..?


### SVG Only
- visiblePainted
- visibleFill
- visibleStroke
- visible
- painted
- fill
- stroke
- all