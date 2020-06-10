---
description: 함수형 컴포넌트에서 hooks를 사용해 상태를 관리
---

# Hooks

## UseState

하나의 상태를 관리할 때 :

```
const [number, setNumber] = useState( 초기값 );

const onClick = () => {
    setNumber(nuber + 1);
};
```

여러 상태값이 필요할 때 :

```bash
const [state, setState] = useState({
    name: '',
    number: ''
});

const onClick = () => {
    setState({
        ...state,
        name: '변경할 값',
        number: '변경할 값'
    })
}
```

{% hint style="warning" %}
객체나 배열에 변화를 줄 때는 불변성을 지켜야 하므로, 복사 후 수정한다.

만약 서로 관련이 없는 상태값이라면, useState를 여러번 사용하자!
{% endhint %}





## UseRef

DOM에 직접적인 접근이 필요할  때:

```
const sample = useRef();

const onClick = () => {
    sample.current.focus();
};

return(
    <input onClick={onClick} ref={sample} />
);
```

{% hint style="info" %}
useRef로 sample 객체를 만들고, 이 객체를 원하는 DOM에 ref로 설정하면

sample.current 의 값이 원하는 DOM이 된다.
{% endhint %}



컴포넌트 안에서 변수를 관리하는 경우 : 

{% hint style="info" %}
const num = useRef\(4\) 

이런식으로 초기값을 정해서 num 이라는 변수이용시에 필요
{% endhint %}



## UseEffect

useEffect\(function\(\), \[array\]\) 

* 함수형 컴포넌트에서 lifecycle 관리할 수 있다.
* componentDidMount, componentDidUpdate, componentWillUnmount
* api를 호출하거나 data를 가져올 수 있다.

```
useEffect(()=>{
   console.log('componentDidMount');
   return () => {
      console.log('componentWillUnmount');
    } 
},[state]);
```

{% hint style="info" %}
line 2 : 일반적으로 렌더링 후 실행되는 코드로 componentDidMount 역할을 한다.

line 4 : re-render 되기 전에 실행이된다. 컴포넌트 종료 시점에. componentWillUnmount
{% endhint %}

{% hint style="danger" %}
\[state\] 파라미터는 해당 상태값이 변경시에만 re-render를 하겠다는 뜻이다.

1. 해당 파라미터가 없으면 모든 상태값이 변할 때 re-render
2. 파라미터가 있을 때는 그 상태값에 변화가 있을 때만 re-render
3. 파라미터가 빈배열이면 
{% endhint %}



