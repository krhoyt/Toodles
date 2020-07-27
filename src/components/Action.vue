<template>
  <button :title="title"></button>
</template>

<script>
export default {
  name: 'Action',
  props: {
    title: {type: String, default: 'Add item'}
  }
}
</script>

<style scoped>
button {
  background: none;
  background-color: #F44336;
  background-image: url( /img/add.svg );
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  border: none;
  border-radius: 56px;
  bottom: 184px;
  box-shadow: 0 2px 5px rgba( 0, 0, 0, 0.26 );
  box-sizing: border-box;
  cursor: pointer;
  height: 56px;
  outline: none;
  position: absolute;
  right: 16px;
  width: 56px;
}

button:hover {
  background-image: url( /img/compose.svg );
}
</style>
