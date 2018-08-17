<template>
  
<div class="fields">

<input type="message" v-model="second_name" placeholder="Фамилия" class="form-control">
<hr>
<input type="message" v-model="name" placeholder="Имя" class="form-control">
<hr>
<input type="message" v-model="patronymic" placeholder="Отчество" class="form-control">
<hr>
<input type="date" :value="myDate" @input="myDate = $event.targer.value" placeholder="Введите дату" class="form-control" />
<br>
  <button 
  class="btn btn-success disabled" 
  @click="switchComponent('fio')"
  :disabled="currentComp === 'fio'"
  >Back</button>
  

<button 
  class="btn btn-success" 
  @click="switchComponent('skills')"
   :disabled="currentComp === 'skills'"
  >Next</button>


   
</div>

</template>

<script>
import { bus } from '../main.js';

export default {
    data() {
      return{
    second_name: '',
    name: '',
    patronymic: '',
    myDate: ''
      }
  },
  props: {
    currentComp: {
      type: String,
      required: true
    }, 
    second_name: String
  },

  methods: {
    switchComponent(comp) {
      bus.$emit('switchComp', comp),
      bus.$emit('login', {
          second_name: this.second_name,
          name: this.name

      })
    }


  }

}
</script>

<style scoped>

.fields{

text-align: center;

}
.btn {

  margin-top: 40px;

}

</style>


