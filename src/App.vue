<template>
  <div id="app">
    <DischiList></DischiList>
  </div>
</template>

<script>
import DischiList from './components/DischiList.vue';



export default {
  name: 'App',
  components: {
    DischiList,
}
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
