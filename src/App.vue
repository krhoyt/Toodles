<template>
  <div id="app">
    <Header/>
    <List/>
    <Bar class="location" icon="/img/location.svg" title="Location">
      <Criteria 
        @click.native="location = 0" 
        :selected="location === 0">
        Any
      </Criteria>
      <Criteria 
        @click.native="location = 1" 
        :selected="location === 1">
        Home
      </Criteria>
      <Criteria 
        @click.native="location = 2" 
        :selected="location === 2">
        Work
      </Criteria>      
    </Bar>
    <Bar class="duration" icon="/img/duration.svg" title="Duration">
      <Criteria
        @click.native="duration = 0" 
        :selected="duration === 0">
        Any
      </Criteria>
      <Criteria
        @click.native="duration = 1" 
        :selected="duration === 1">
        &lt; 30 mins.
      </Criteria>      
      <Criteria
        @click.native="duration = 2" 
        :selected="duration === 2">
        30 - 60 mins.
      </Criteria>            
      <Criteria
        @click.native="duration = 3" 
        :selected="duration === 3">
        1 - 2 hrs.
      </Criteria>                  
      <Criteria
        @click.native="duration = 4" 
        :selected="duration === 4">
        2 - 4 hrs.
      </Criteria>                  
      <Criteria
        @click.native="duration = 5" 
        :selected="duration === 5">
        &gt; 4 hrs.
      </Criteria>                  
    </Bar>
    <Bar class="energy" icon="/img/energy.svg" title="Energy">            
      <criteria
        @click.native="energy = 0" 
        :selected="energy === 0">
        Any
      </Criteria>            
      <Criteria
        @click.native="energy = 1" 
        :selected="energy === 1">
        Low
      </Criteria>            
      <Criteria
        @click.native="energy = 2" 
        :selected="energy === 2">
        Normal
      </Criteria>            
      <Criteria
        @click.native="energy = 3" 
        :selected="energy === 3">
        High
      </Criteria>                  
    </Bar>
    <Action/>
  </div>
</template>

<script>
import Action from './components/Action.vue';
import Bar from './components/Bar.vue';
import Criteria from './components/Criteria.vue';
import Header from './components/Header.vue';
import List from './components/List.vue';

export default {
  name: 'App',
  components: {
    Action,
    Bar,
    Criteria,
    Header,
    List
  },
  data() {
    return {
      duration: 0,
      energy: 0,
      location: 0
    };
  }
}
</script>

<style>
#app {
  background-color: #FAFAFA;  
  color: rgba( 0, 0, 0, 0.87 );
  display: flex;
  flex-basis: 0;
  flex-direction: column;
  flex-grow: 1;
  font-family: 'Roboto', sans-serif;  
  margin: 0;
  overflow: hidden;
  padding: 0;    
}

.duration {
  border-top: 1px solid rgba( 0, 0, 0, 0.12 );
}

.energy {
  border-top: 1px solid rgba( 0, 0, 0, 0.12 );  
}

.location {
  box-shadow: 0 0 5px rgba( 0, 0, 0, 0.26 );
}
</style>
