## 💡 this 키워드

### this란?

- **자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수**다.
  - this를 통해 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있다.
  - this 바인딩은 **함수 호출 방식에 의해 동적으로 결정**된다.

### ✨ 함수 호출 방식과 this 바인딩

- 함수가 어떻게 생겼던 간에 **이 함수를 어떻게 호출하느냐**에 따라 안에있는 this에 바인딩 되는 값이 달라진다!!
  ```jsx
  // foo 함수
  const foo = function(){ console.log(this) }
  ```
- 함수 호출 방식
  1. 일반 함수 호출 : this → 전역객체

     1. 일반 함수로 호출된 모든 함수(중첩 함수, 콜백 함수 포함)

     ```jsx
     // 일반 함수로 호출
     foo() // this => 전역객체
     ```

  2. 메서드 호출 : this → 자신을 가리키는 객체

     ```jsx
     const obj = {foo}
     // 메서드로 호출
     obj.foo() // this => obj
     ```

  3. 생성자 함수 호출 : this → 생성될 인스턴스

     ```jsx
     // 생성자 함수로 호출
     new foo() // this => 생성될 객체
     ```

     - 함수앞에 new 키워드를 붙여서 호출하면 생성자 함수 호출

  4. Function.prototype.apply/call/bind 메서드에 의한 간접 호출 : this → 내가정함

     ```jsx
     const bar = { name:bar }
     foo.call(bar) // this => bar
     foo.apply(bar) // this => bar
     foo.bind(bar)() // this => bar
     ```

     - 함수안에 있는 this를 이 객체로 지정하겠다
