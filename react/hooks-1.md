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

* function : render 또는 re-render 시에 실행하고 싶은 함수

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

여러 상태값이 필



