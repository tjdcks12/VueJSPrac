## [VueJS] data binding

 

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8">
    <title>data binding practice</title>
  </head>
  <body>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js">	</script>
    <script>
      new Vue({
        el: '#app'
      })
    </script>

  </body>
</html>

```

Vue는 script 형태의 import만으로 동작 가능하다. cdn주소를 통해서 import 한 후, Vue 객체를 생성하고, el(엘리먼트) 어트리뷰트값에 DOM 셀렉터를 매칭시켜주면 사용할 수 있습니다.



### data() & v-model

data() 함수의 리턴 블록내에 인스턴스내부에서 사용할 데이터를 정의할 수 있습니다. 또한, 이를  태그 내의 v-model 이라는 어트리뷰트를 설정함으로써 동기화 시킬 수 있습니다. 

```html
<input type="text" id="user_id" v-model="userId"/>
<input type="password" id="user_password" v-model="userPassword"/>
<button type="button">로그인</button>

<script>
new Vue({
  el: '#app',
  data() {
    return {
      userId: '',
      userPassword: ''
    }
  }
})
</script>
```



### {{ data }}

중괄호를 활용함으로써 데이터 값을 html 상에 출력할 수 있습니다.

```
<li>
아이디 : {{ userId }}
비밀번호 : {{ userPassword }}
</li>
```

이러한 식의 표현방법은 데이터값이 변경될때마다 동적으로 변경되기 때문에, 기존에 onChange 함수 등을 활용하여 구현해야 하는 부분을 간단하게 구현 가능하게 되었습니다.



### 정리

Vue 에서는 백엔드 프레임워크에서 지원하는 MVC아키텍쳐와 같이 화면 구성에 필요한 **모델**과 화면을 표현하는 **뷰** 로 분리되는 특징을 가지고 있습니다. 

기존에 사용자가 일일히 구현해주어야 했던 자바스크립트 코드를 뷰 엔진에서 담당하고, 사용자는 보다 직관적으로 데이터와 데이터를 표현하는 DOM 구조에 집중할수 있게 되었다고 생각합니다.

