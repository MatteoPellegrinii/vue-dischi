<template>
  <div id="app">
    <DischiList>
    </DischiList>
  </div>
</template>

<script>
import DischiList from './components/DischiList.vue';



export default {
  name: 'App',
  components: {
    DischiList
}
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app{
  background-color: rgb(0, 0, 85);
  height: 100vh;
}
</style>
