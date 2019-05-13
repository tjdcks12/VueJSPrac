## [VueJS] attribute binding



### String이 결합된 attribute binding

스트링과 결합된 어트리뷰트 바인딩은 다음과 같은 방식으로 할 수 있습니다.

```html
<div id="app">
  <img :id="`thumbnail_${id}`" :src="image" />
</div>

<script>
  let app = new Vue({
    el: '#app',
    data() {
      return {
        id: 1,
        image: "https://naver.com"
      }
    }
  })
</script>
```



### style attribute binding

style 속성또한 다음과 같은 방식으로 바인딩이 가능합니다.

```html
<div id="app">
  <div :style="style">
    test
  </div>
</div>
<script>
  let app = new Vue({
    el: '#app',
    data() {
      return {
        style: 'background : white'
      }
    }
  })
</script>
```



#### Json 형태 & 다중 속성 삽입

배열 형태로 다양한 어트리뷰트 속성값을 지정할 수 있습니다.

```html
<div id="app">
  <div :style="[style, fontStyle]">
    test
  </div>
</div>
<script>
  let app = new Vue({
    el: '#app',
    data() {
      return {
        id: 1,
        style: {
          background: 'red',
          fontSize: '10px',
          fontFamily: 'dotum'
        },
        fontStyle: {
        	fontSize: '10px',
        	fontFamily: 'dotum'
        }
      }
    }
  })
</script>
```

