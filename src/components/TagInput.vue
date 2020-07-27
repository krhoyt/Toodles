<template>
  <div class="tags">
    <div class="icon" title="Tags"></div>
    <div class="added">
      <Tag 
        @clear="doClear"
        :editable="true"
        :key="index"
        :label="tag"
        v-for="( tag, index ) in tags"/>
    </div>
    <input :placeholder="placeholder" type="text" v-on:keyup.enter="doEnter" v-model="label">
  </div>
</template>

<script>
import Tag from './Tag.vue';

export default {
  components: {
    Tag
  },
  name: 'TagInput',
  props: {
    placeholder: {type: String, default: 'Tags'},
    tags: {type: Array, default() {
      return [];
    } }
  },
  data() {
    return {
      label: null
    };
  },
  methods: {
    doClear( label ) {
      let index = -1;

      for( let t = 0; t < this.tags.length; t++ ) {
        if( this.tags[t] === label ) {
          index = t;
          break;
        }
      }

      this.tags.splice( index, 1 );
    },
    doEnter() {
      this.tags.push( this.label );
      this.tags.sort();
      this.label = null;
    }
  }
}
</script>

<style scoped>
div.added {
  align-items: center;
  display: flex;
  flex-direction: row;
}

div.icon {
  background-image: url( /img/tag.svg );
  background-position: left 12px center;
  background-repeat: no-repeat;
  background-size: 24px;  
  height: 48px;
  opacity: 0.54;
  width: 48px;  
}

div.tags {
  border-top: solid 1px rgba( 0, 0, 0, 0.12 );  
  box-sizing: border-box;
  display: flex;
  flex-basis: 0;
  flex-direction: row;
  flex-grow: 1;
}

input[type="text"] {
  background: none;
  border: none;
  box-sizing: border-box;
  color: rgba( 0, 0, 0, 0.87 );    
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
  flex-basis: 0;
  flex-grow: 1;
  outline: none;
  height: 48px;
}

input[type="text"]::placeholder {
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
}
</style>
