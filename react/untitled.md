---
description: react를 개발하면 자주 사용하는 것
---

# Tip.

## 1. 조건부 렌더링

```text
// 다음와 같이 둘 중 하나의 결과를 보여줘야 한다면 삼항연산자
return (
    <div>
        {isTrue ? <p>true</p> : <p>false</p>}
    </div>
);
```

```text
// 참거짓에 대한 값으로 보여주고 숨겨주고의 결과를 원한다면 다음과 같이 실
return (
    <div>
        {isTrue &&  <p>true</p>}
    </div>
);
```



## 2. props

```text
function Sub({name}){                // (name)으로 가져온다면
   return <div>{name}</div>          // {name.name}으로 사용해야 한다.
}

function Main(){
    return <Sub name='donald' />
}
```



## 3. 배열의 렌더링

```text

```



