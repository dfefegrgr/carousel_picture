<template>
<div class="b" v-for="a in number" >
  {{ a }}
<!--  <img src="../assets/{{ a }}.jpg" />-->
</div>
</template>

<script>
import {defineComponent} from "vue";
export default defineComponent({
  name:'leftbox',
  props:{
    number:{
      type:Object,
      required:true
    }
  }
})

</script>


<style scoped lang="scss">
.b{
  width: 400px;
  height: 500px;
  background-size: cover;
}
</style>