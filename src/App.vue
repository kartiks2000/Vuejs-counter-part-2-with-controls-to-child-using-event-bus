<template>
  <div>
    <h1>I am parent component....</h1>
    <h1>Counter: {{c}}</h1>
    <button @click="inc">Increment</button>
    <button @click="dec">Decrement</button>
    <Child :c="c"></Child>
  </div>
</template>

<script>
import { mybus } from './main';
import Child from './Components/child';
export default {
  components:{
    Child : Child
  },
  data:function(){
    return{
      c : 0
    }
  },
  methods:{
    inc(){
      this.c += 1;
    },
    dec(){
      this.c -= 1;
    }
  },
  created(){
    mybus.$on("in",() => this.inc());
    mybus.$on("de",() => this.dec());
  }
}
</script>

<style scoped>
  .ch{
        background-color: rgb(167, 155, 155);
        padding: 2rem;
        margin: 5rem;
    }
</style>