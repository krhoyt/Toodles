<template>
  <div class="area">
    <div class="icon" :title="placeholder"></div>
    <textarea :placeholder="placeholder"></textarea>
  </div>
</template>

<script>
export default {
  name: 'TextArea',
  props: {
    placeholder: {type: String, default: 'Notes'}
  }
}
</script>

<style scoped>
div.area {
  border-top: solid 1px rgba( 0, 0, 0, 0.12 );    
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
}

div.icon {
  background-image: url( /img/note.svg );
  background-position: center;
  background-repeat: no-repeat;
  background-size: 24px;
  box-sizing: border-box;
  height: 48px;
  opacity: 0.54;
  width: 48px;
}

textarea {
  background: none;
  border: none;
  box-sizing: border-box;
  color: rgba( 0, 0, 0, 0.87 );      
  flex-basis: 0;
  flex-grow: 1;
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
  height: 100px;
  margin: 0;
  outline: none;
  padding: 14px 16px 0 0;
  resize: none;
}

textarea::placeholder {
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
}
</style>
