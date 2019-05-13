## [VueJS] component



동일한 포맷이 반복되는 템플릿의 경우 기존의 html 코드로 표현하면 그 포맷의 갯수만큼 코드길이가 늘어났다. 하지만 VueJS에서는 이를 Component를 통해 관리할 수 있다.



```vue
<script>
Vue.component('product', {
  props: ['image', 'title', 'description', 'avatar'],
  template: `
    <div>
      <div>
        <img :src="image" />
        <img :src="avatar" width="30" />
      </div>
      <div>
        {{ title }}
      </div>
      <p>
        {{ description }}
      </p>
    </div>
  `
});
</script>
```



Vue.component 함수를 통해 컴포넌트를 생성하고, 첫번째 인자로 컴포넌트 이름, 두번째 인자로는 템플릿에 사용될 변수값을 **props**, 틀을 **template** 이라는 속성 값으로 하는 객체를 넣어주면 됩니다.

중요한 점은 template에 선언되는 html 틀의 경우 VueJS 기본 기능들이 모두 동일하게 동작하기 때문에 편리하게 사용 가능하다는 점입니다.
