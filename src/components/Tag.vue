<template>
  <div>
    <p>{{label}}</p>
    <button @click="doClear" v-show="editable"></button>
  </div>
</template>

<script>
export default {
  name: 'Tag',
  props: {
    editable: {type: Boolean, default: false},
    label: {type: String, default: null}
  },
  methods: {
    doClear() {
      this.$emit( 'clear', this.label );
    }
  }
}
</script>

<style scoped>
button {
  background: none;
  background-image: url( /img/cancel.svg );
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  border: none;
  cursor: pointer;
  height: 24px;
  margin-right: 2px;
  opacity: 0.54;
  width: 24px;
}

button:hover {
  opacity: 1;
}

div {
  align-items: center;
  background-color: rgba( 0, 0, 0, 0.12 );
  border-radius: 32px;
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
  height: 32px;
  margin: 0 16px 0 0;
  padding: 0 0 0 12px;
}

p {
  box-sizing: border-box;
  color: rgba( 0, 0, 0, 0.87 );
  cursor: default;
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
  height: 32px;
  line-height: 32px;
  margin: 0;
  padding: 0 12px 0 0;
}
</style>
