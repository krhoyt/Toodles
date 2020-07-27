<template>
  <div class="detail">
    <TagInput/>
    <div class="options">
      <input type="date">
      <Select class="border" icon="/img/location.svg"/>
      <Select class="border" icon="/img/duration.svg"/>
      <Select icon="/img/energy.svg"/>
    </div>
    <TextArea/>
  </div>
</template>

<script>
import Select from './Select.vue';
import TagInput from './TagInput.vue';
import TextArea from './TextArea.vue';

export default {
  components: {
    Select,
    TagInput,
    TextArea
  },
  name: 'Detail',
  props: {
    title: {type: String, default: 'Toodles'}
  }
}
</script>

<style scoped>
div.detail {
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
}

div.options {
  border-top: solid 1px rgba( 0, 0, 0, 0.12 );  
  display: flex;
  flex-direction: row;
}

input[type="date"] {
  background: none;
  border: none;
  border-right: solid 1px rgba( 0, 0, 0, 0.12 );    
  box-sizing: border-box;
  min-height: 48px;
  width: 194px;
}

input[type="text"] {
  background: none;
  background-image: url( /img/tag.svg );
  background-position: left 12px center;
  background-repeat: no-repeat;
  background-size: 24px;
  border: none;
  border-top: solid 1px rgba( 0, 0, 0, 0.12 );
  box-sizing: border-box;
  min-height: 48px;
  flex-basis: 0;
  flex-grow: 1;
  margin: 0;
  padding: 0;
}

.border {
  border-right: solid 1px rgba( 0, 0, 0, 0.12 );      
}
</style>
