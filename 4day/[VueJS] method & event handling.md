## [VueJS] method & event handling

### method

메소드는 특정 객체에 포함되어 동작한다. VueJS에서는 메소드 선언을 Vue 객체에 methods 라는 어트리뷰트를 선언함으로써 생성 가능합니다.

<br/>

주의할점이 하나 있는데, VueJS 에서 메소드선언에서는 arrow function이 사용되면 안됩니다.

<br/>

그 이유는 methods 영역에  arrow function 선언시 this 바인딩이 안되므로, data()함수에 정의된 변수값에 접근이 불가능 하기 때문입니다.



```vue
<script>
new Vue({
  el: '#app',
  data() {
    return {
      counter: 0
    };
  },
  methods: {
    add: () => {
      this.counter++;
      console.log(this.counter);
    }
  }
})
</script>
```

<sub>위와같이 작성시 원하는대로 동작하지 않음</sub>



```vue
<script>
  new Vue({
    el: '#app',
    data() {
      return {
        counter: 0
      };
    },
    methods: {
      add() {
        this.counter++;
        console.log(this.counter);
      }
    }
  })
</script>
```

<sub>제대로 동작하는 코드</sub>





### event handling



```html
<div id="app">
    <button type="button" v-on:click="add">더하기 </button>
    {{ counter }}
</div>
```

위와같은 click 이벤트 생성시 **v-on:click**이후 영역은 javascript 코드 영역이므로, 연사자 실행이 가능합니다. 예를들어서 data() 영역에 선언된 counter 변수의 값을 click 이벤트로 증가시키는 등의 코드를 생성하고 싶다면



```html
<div id="app">
  <button type="button" v-on:click="counter++">더하기 </button>
  {{ counter }}
</div>
```

위와 같이 입력하여 동작시킬 수 있습니다.

 또한 이벤트 관련 지시자의 경우 이전 챕터에서 v-bind 를  **:** 로 줄여쓴 것처럼,  **@** 를 입력함으로써 줄여 쓸 수 있습니다.


```html
<div id="app">
    <button type="button" @click="add">더하기 </button>
    {{ counter }}
</div>
```



또한 이벤트의 특정 실행 조건을 프로퍼티로 제공하므로 해당 프로퍼티를 학습하면 기존에 자바스크립트를 통해 복잡하게 구현하던 부분들을 간편하게 구현 가능합니다.

```html
<input type="text" @keyup.enter="keyup"/>
```

```vue
<script>
methods: {
  keyup(ev) {
    console.log(ev);
    alert("엔터키 눌렸습니다 ^^");
  }
  /*if (ev.keyCode === 13) {
    console.log('엔터키 눌렸습니다 ^^');
  }*/
}
</script>
```

