<template>
  <div class="bar">
    <div class="left" :style="styles" :title="title"></div>
    <div class="list">      
      <slot></slot>
    </div>
    <div class="right"></div>
  </div>
</template>

<script>
export default {
  name: 'Bar',
  props: {
    icon: {type: String, default: null},
    title: {type: String, default: null}
  },
  computed: {
    styles() {
      return {
        backgroundImage: this.icon === null ? '' : `url( ${this.icon} )`
      };
    }
  }
}
</script>

<style scoped>
div {
  box-sizing: border-box;
}

div.bar {
  align-items: center;
  background-color: #ffffff;
  display: flex;
  flex-direction: row;  
}

div.left {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  height: 56px;
  opacity: 0.56;
  width: 56px;
}

div.list {
  box-sizing: border-box;
  display: flex;
  flex-basis: 0;
  flex-direction: row;
  flex-grow: 1;
  justify-content: center;
}

div.right {
  height: 56px;
  width: 56px;
}
</style>
