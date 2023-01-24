# radial-gradient

> Safari에서 `at` 문법은 현재(2023.01.24) 지원하지 않는다.

방사형(radial)로 퍼지는 그라데이션 이미지를 추가하는 경우에 유용하게 사용된다.

기본적인 원형(`circle at 50%`)
을 이용하거나, 

일그러진 원형(`ellipse at bottom`)
을 사용할 수 있다.

## Formal syntax
```
<radial-gradient()> = 
  radial-gradient ( [<ending-shape> || <size>]? [at <position>]?, <color-stop-list> )


<size> = 
  <extent-keyword>                | 
  <length, [0, infi]>             |
  <legnth-percentage [0, infi]>{2}


<position> = 
  [ left | center | right ] || [ top | center | bottom ] |
  [ left | center | right |<length-percentage> ] [ top | center | bottom | <length-percentage>? | ...]
```