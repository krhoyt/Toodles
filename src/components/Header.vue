<template>
  <p>{{title}}</p>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: {type: String, default: 'Toodles'}
  }
}
</script>

<style scoped>
p {
  background-color: #2196F3;
  box-sizing: border-box;
  box-shadow: 0 2px 5px rgba( 0, 0, 0, 0.26 );
  color: #ffffff;
  cursor: default;
  font-family: 'Roboto', sans-serif;
  font-size: 20px;
  height: 56px;
  line-height: 56px;
  margin: 0;
  padding: 0 0 0 16px;
}
</style>
