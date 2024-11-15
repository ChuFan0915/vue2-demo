<template>
  <div id="app">
    <MySearch></MySearch>
    <MyList></MyList>
  </div>
</template>

<script>
import MyList from './components/MyList.vue';
import MySearch from './components/MySearch.vue';

export default {
  name: 'App',
  components: {
    MyList,MySearch
  }
}
</script>

<style>
body{
  margin: 0;
  padding: 0;
}

</style>
