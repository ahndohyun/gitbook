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
function Sub({name}){           
   return <div>{name}</div>      
}

function Main(){
    return <Sub name='donald' />
}
```

{% hint style="danger" %}
만약 props를 \(name\)으로 가져온다면 return 값에 들어갈 내용은 &lt;div&gt;{name.name}&lt;/div&gt;

props는 객체형태로 전달되기 때문.
{% endhint %}



## 3. 배열의 렌더링

```text
const arr = [1,2,3];

return (
    <div>
        {arr.map((ele,index) => (
            <div key={index}>{ele}</div>
        ))}
    </div>
);
```



