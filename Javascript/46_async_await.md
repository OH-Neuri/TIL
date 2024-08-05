## 💡 46장. async/await

### async/await

- ES8에서 간단하고 가독성 좋게 비동기 처리를 동기 처리처럼 동작하도록 구현할 수 있는 async/await 도입
- 프로미스의 후속처리 없이 마치 **동기처럼 프로미스 처리할 수있도록 구현**

### async

- async 함수는 **언제나 프로미스를 반환**한다.
- 명시적으로 프로미스를 반환하지 않아도 **반환값을 resolve하는 프로미스를 반환**한다.

```tsx
 async function foo(n){return n}
 foo(1).then(v=>console.log(v)) //1
```

### await

- await 키워드는 반드시 async 함수 내부에서 사용해야 한다.
- await 키워드는 프로미스가 settled 상태가 될 때까지 대기하다가 settled 상태가 되면 프로미스가 resolve한 처리 결과를 반환한다.
- await는 반드시 프로미스 앞에서 사용해야한다.

### 에러처리

- 프로미스를 반환하는 비동기 함수를 명시적으로 호출할 수 있기 떄문에 try~catch 문이 가능하다
- async 함수내에서 catch문을 사용하지 않으면 발생한 에러를 reject하는 프로미스를 반환한다.
