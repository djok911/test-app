<template>
  <div>
    <h3>Summary</h3>
      <h1>{{this.second_name}}</h1>
    </div>
  
</template>

<script>

import { bus } from '../main.js';

export default {
  props: ['second_name'],
   
      
   }

</script>

<style scoped>

</style>