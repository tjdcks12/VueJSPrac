## [VueJS] event bus

서로 연관없는 컴포넌트간에 데이터를 주고받을경우 사용하는 방법이다.



뷰에는 기본적인 이벤트 관련 기능이 구현되어있기 때문에 뷰 인스턴스를 별도로 만들어 각 컴포넌트에서 이벤트를 발생시키고 받아오는 도구로 사용하는 것입니다.



```vue
<script>
import Vue from 'vue';
const bus = new Vue();

export default {
  methods: {
    makeEvent() {
        bus.$emit('BUTTON-CLICK', 'data'); //이벤트 버스로부터
    }
  },
  created() {
    bus.$on('BUTTON-CLICK', data => {
      console.log(data);
    })
  }
}
</script>
```





기능이 많아지고 코드가 복잡할수록 어떤 이벤트를 발생시키는지 확인하기 어렵기때문에 대규모 프로젝트에서는 vuex라는 라이브러리를 이용해서 컴포넌트간 데이터를 주고받는 기능을 사용합니다.

vuex를 이용하면 이벤트간에 구조를 잡아 어떤 이벤트를 사용중인지 쉽게 파악할수 있으며 로그인한 유저정보등과 같이 전역적으로 사용되는 데이터를 한곳에 모아서 간편하게 사용할 수 있도록 합니다.