<template>
  <div class="row">
    <div class="item">
      <input type="checkbox">
      <input @focus="open = true" type="text" :value="title">
      <div class="tags" v-show="!open">
        <Tag v-for="( tag, index ) in tags" :key="index" :label="tag"/>
      </div>
      <div class="rule"></div>
      <button @click="doDelete" title="Delete"></button>
    </div>
    <Detail v-show="open"/>
  </div>
</template>

<script>
import Detail from './Detail.vue';
import Tag from './Tag.vue';

export default {
  components: {
    Detail,
    Tag
  },
  name: 'Item',
  props: {
    completed: {type: Boolean, default: false},    
    title: {type: String, default: 'New To Do'},
    tags: {type: Array, default() {
      return [];
    } }
  },
  data() {
    return {
      open: false
    };
  },
  methods: {
    doDelete() {
      console.log( 'DELETE' );
    }
  }
}
</script>

<style scoped>
button {
  background: none;
  background-image: url( /img/trash.svg );
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  border: none;
  box-sizing: border-box;
  cursor: pointer;
  height: 24px;
  margin: 0 12px 0 12px;
  opacity: 0.54;
  outline: none;
  padding: 0;  
  position: relative;
  width: 24px;
}

button:hover {
  opacity: 1;
}

div.item {
  align-items: center;
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
}

div.row {
  background-color: #ffffff;
  border-radius: 2px;  
  box-shadow: 0 2px 5px rgba( 0, 0, 0, 0.26 );
  box-sizing: border-box;
}

div.rule {
  background-color: rgba( 0, 0, 0, 0.12 );
  height: 48px;
  width: 1px;
}

div.tags {
  display: flex;
  flex-direction: row;
}

input[type="checkbox"] {
  appearance: none;
  background: none;
  background-image: url( /img/checkbox-outline.svg );
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  border: none;
  box-sizing: border-box;
  cursor: pointer;
  height: 24px;
  margin: 0 12px 0 12px;
  opacity: 0.54;
  outline: none;
  padding: 0;
  width: 24px;
}

input[type="checkbox"]:checked {
  background-image: url( /img/checkbox.svg );
}

input[type="checkbox"]:hover {
  opacity: 1;
}

input[type="text"] {
  background: none;
  border: none;
  box-sizing: border-box;
  color: rgba( 0, 0, 0, 0.87 );
  cursor: default;
  font-family: 'Roboto', sans-serif;
  font-size: 16px;
  height: 48px;
  flex-basis: 0;
  flex-grow: 1;
  line-height: 48px;;
  margin: 0 16px 0 0;
  outline: none;
  padding: 0;
}
</style>
