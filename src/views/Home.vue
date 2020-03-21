<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <LoadMoreContent id="loadMore" classname="list" count="2" :datas='[{id: 1, content: "1"}, {id: 2, content: "2"}, {id: 3, content: "3"}, {id: 4, content: "4"}, {id: 5, content: "5"}]'/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import LoadMoreContent from '@/components/load-more-content.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
    LoadMoreContent
  }
}
</script>
