<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <span class="navbar-brand"> 채팅리스트 </span>
  <ul class="navbar-nav mr-auto">
  </ul>
  <button type="button" class="btn btn-white">
    <i class="fa fa-envelope mr-2"></i>
    <span class="badge badge-danger">{{ newMessageCount }}</span>
  </button>
</nav>
</template>
<script>
export default {
  props: ['newMessageCount']
}
</script>
