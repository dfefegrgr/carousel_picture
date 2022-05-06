<template>
  <div class="home">
    <div class="box">
      <div class="box_leftbox">
        <leftbox :number="number" ></leftbox>
      </div>
      <div class="box_rightbox">
        <rightbox/>
      </div>
    </div>


  </div>
</template>

<script>

import leftbox from "@/components/leftbox";
import rightbox from "@/components/rightbox";
import {useStore} from 'vuex';
export default {
  name: 'HomeView',
  components: {
    rightbox,
    leftbox
  },
  setup(){
    let store=useStore()
    let number = computed(()=>{
      return store.state.number
    })
    return{
      number
    }
  }
}
</script>

<style>
.home{
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  background-color: #b5cad9;
  width: 100%;
  height: 100%;
}
.box{
  display: flex;
  justify-content: space-evenly;
  width: 650px;
}
</style>
