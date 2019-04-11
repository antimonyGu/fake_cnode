<template>
  <div id="app">
    <Header></Header>
    <div class="main">
      <Postlist></Postlist>
    </div>
  </div>
</template>

<script>
import Header from './components/header'
import Postlist from './components/postlist'
export default {
  name: 'App',
  components:{
    Header,
    Postlist
  }
}
</script>

<style>
.main {
  width: 80%;
  margin: 0 auto;
}
</style>
