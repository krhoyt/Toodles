<template>
  <button :class="{selected: selected}">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'Criteria',
  props: {
    selected: {type: Boolean, default: false}
  }
}
</script>

<style scoped>
button {
  background: none;
  border: none;
  border-top: solid 2px transparent;
  box-sizing: border-box;
  cursor: pointer;
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
  font-weight: 500;
  height: 56px;
  margin: 0;
  outline: none;
  padding: 0;
  width: calc( 100% / 7 );
}

button.selected {
  background-color: #E3F2FD;
  border-top: solid 2px #2196F3;
  color: #2196F3;
  font-weight: 500;  
}
</style>
