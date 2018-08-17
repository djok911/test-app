<template>
  <div class = "contact">

      <input type="email" v-model="email" placeholder="Enter email" class="form-control">
      <hr>
      <input type="tel" v-model="tel" placeholder="Введите свой номер телефона" class="form-control">
        <button 
        class="btn btn-success" 
        @click="switchComponent('skills')"
        :disabled="currentComp === 'skills'"
        >Back</button>
        <button 
        class="btn btn-success" 
        @click="switchComponent('sum-info')"
        :disabled="currentComp === 'sum-info'"
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

.contact {
  text-align: center;
}

.btn-success {
  margin-top: 20px;
}

</style>


