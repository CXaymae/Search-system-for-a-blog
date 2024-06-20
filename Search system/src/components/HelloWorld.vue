<template>
  <div>
    <h2> Filter Technical Articles </h2>
    <input 
     type='text' 
     placeholder='Filter Search' 
     v-model='query'
   />
   <br>
   <button @click='reset'> Reset </button>
   <search-results :query='query'/>
  </div>
</template>

<script>
 import { ref } from 'vue'
 import Results from './Results.vue'
 export default {
   components: {
     Results
   },
   setup () {
     const query = ref('')

     const reset = (evt) => {
       query.value = '' // clears the query
     }
     
     return {
       reset,
       query
     }
   }
 }
</script>

<style>
 input[type='text'] {
   margin-bottom: 20px;
   padding: 10px;
 }
</style>
