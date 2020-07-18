<template>
  <div class="ch">
      <h1>I am child component...</h1>
    <h1>Counter: {{c}}</h1>
    <button @click="incme">Increment</button>
    <button @click="decme">Decrement</button>
  </div>
</template>

<script>
import { mybus } from '../main';;
export default {
    props: ["c"],
    methods:{
        incme(){
            mybus.$emit("in");
        },
        decme(){
            mybus.$emit("de");
        }
    }
}
</script>

<style scoped>
    
</style>