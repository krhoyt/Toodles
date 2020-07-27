<template>
  <div class="select">
    <div class="icon" :style="styles"></div>
    <p>{{label}}</p>
    <div class="arrow"></div>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: {
    icon: {type: String, default: null},
    label: {type: String, default: 'Any'}
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
div.arrow {
  background-image: url( /img/arrow.svg );
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  cursor: pointer;
  height: 48px;
  opacity: 0.54;
  width: 48px;
}

div.icon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  cursor: pointer;
  height: 48px;
  opacity: 0.54;
  width: 48px;
}

div.select {
  background: none;
  background-position: left 12px center;
  background-repeat: no-repeat;
  background-size: 24px;  
  box-sizing: border-box;
  display: flex;
  flex-basis: 0;
  flex-direction: row;
  flex-grow: 1;
}

p {
  color: rgba( 0, 0, 0, 0.87 );  
  cursor: pointer;
  flex-basis: 0;
  flex-grow: 1;
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
  height: 48px;
  line-height: 48px;
  margin: 0;
  padding: 0;
}
</style>
