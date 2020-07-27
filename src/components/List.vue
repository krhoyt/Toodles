<template>
  <div>
    <Item :tags="['goes', 'here', 'stuff']"/>
  </div>
</template>

<script>
import Item from './Item.vue';

export default {
  components: {
    Item
  },
  name: 'List',
  props: {
    title: {type: String, default: 'Toodles'}
  }
}
</script>

<style scoped>
div {
  box-sizing: border-box;
  flex-basis: 0;
  flex-grow: 1;
  margin: 16px 60px 0 16px;
  padding: 0;
}
</style>
