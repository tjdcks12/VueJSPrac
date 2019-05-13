## [VueJS] list



### v-for

VueJS 데이터에는 리스트형태의 데이터를 담을 수 있습니다. 또한 이를 html 에서 순회시키기 위한 **v-for** 어트리뷰트를 지원합니다.

```html
<div id="app">
  <li v-for="item in items">
    {{ item.id }}
  </li>
</div>
<script>
  new Vue({
    el: '#app',
    data() {
      return {
        items : [
          {
            id: 1,
            image: '...'
          },
          {
            id: 2,
            image: '...'
          }
        ]
      }
    }
  })

</script>
```



### v-bind & :attribute

VueJS에서는 태그와 어트리뷰트에 변수값을 대입시키기 위해 v-bind 혹은 :어트리뷰트명 표현식을 활용합니다.

```html
<li v-for="item in items">
  {{ item.id }}
  <img v-bind:src="item.image" />
  <img :src="item.image" />  
  <!-- 위 두개는 동일한 표현 -->

</li>
```





### template 태그

for loop를 각각의 태그속에서 동작시키고 싶을때에는 **template 태그**를 활용하면 됩니다.

```html
<template v-for="item in items">
  <li>
    {{ item.id }}
  </li>
  <li>
    <img :src="item.image" />
  </li>
</template>
```





### 동적으로 List 추가

외부 플러그인 없이 동적으로 새로운 list를 구현하기 위해서는 자바스크립트 코드를 통해 DOM을 구현하고 그에 맞는 텍스트를 직접 스트링형태로 추가하고 append 해주는 방식을 통해 가능했습니다. VueJS에서는 data() 함수에 정의된 변수값에 데이터만 추가해주면 동적으로 list가 append 됩니다.

이를 보여주기 위한 예시는 다음과 같습니다( 다음은 위의 예시를 위해 Vue객체에 변수할당을 했지만, 실제로 추천되는 방법은 아닙니다)





```js
let app = new Vue({
  el: '#app',
  data() {
    return {
      items : [
        {
          id: 1,
          image: 'https://www.google.com/url?sa=i&source=images&cd=&ved=&url=https%3A%2F%2Ftwitter.com%2Fgooglekorea&psig=AOvVaw16SeSEDgigBw1tSk64PIPF&ust=1557758223504154'
        },
        {
          id: 2,
          image: 'http://image.itdonga.com/files/2013/12/09/1.png'
        }
      ]
    }
  }
})

app.items.push({id: 3, image: "..."});
//위 명령어를 콘솔에 실행시 동적으로 li 태그 추가됨
```



