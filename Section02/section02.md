# Section02 자바스크립트 새로고침

## 리액트 프로젝트 구축 프로세스

리액트 프로젝트에서 빌드 프로세스를 사용하는 이유

1\) 처리되지 않은 리액트 코드`JSX`는 브라우저에서 실행할 수 없음

2\) 작성한 코드가 프로덕션을 위해 최적화되지 않았기 `간소화`때문

## "import" 및 "export"

```
export let 변수 및 함수의 이름 = "example";
```

```
import {변수 및 함수의 이름} from "상대 경로"
```

> react로 할 때는 상대 경로에 파일 확장자를 적지 않아도 됨 -> 뒤에서 작동하는 빌드 프로세스가 확장자를 추가하기 때문

```
export default "example"
```

```
import 이름_할당 from "상대 경로"
```

> 이름을 할당하지 않고 그냥 값을 export
>
> 이 파일에서 export한 기본 값이 됨
>
> 파일별로 하나의 값만 default export할 수 있음

```
import {변수1, 함수2} from "상대 경로"
```

```
import * as util from "상대 경로"

console.log(util.변수1)
```
