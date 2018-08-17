<template>
  <div class="skill">
    <label>Ваши профессиональные навыки:</label>
      <textarea v-model="comment" class="form-control"></textarea>
     
  <button 
  class="btn btn-success" 
  @click="switchComponent('fio')"
  :disabled="currentComp === 'fio'"
  >Back</button>
  
  <button 
  class="btn btn-success" 
  @click="switchComponent('contact')"
  :disabled="currentComp === 'contact'"
  >Next</button>
  
  </div>
  
</template>

<script>
import { bus } from '../main.js';

export default {
  props: {
    currentComp: {
      type: String,
      required: true
    }
  },

  methods: {
    switchComponent(comp) {
      bus.$emit('switchComp', comp);
    }
  }
}
</script>

<style scoped>

.skill {
  text-align: center;
}

.btn-success {
  margin-top: 20px;
}


</style>


