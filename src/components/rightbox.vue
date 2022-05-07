<template>
  <div class="c">
        <div class="d dd"><img src="../assets/1.jpg" alt=""> </div>
        <div class="d"><img src="../assets/2.jpg" alt=""> </div>
        <div class="d"><img src="../assets/3.jpg" alt=""> </div>
        <div class="d"><img src="../assets/4.jpg" alt=""> </div>
        <div class="d"><img src="../assets/5.jpg" alt=""> </div>

  </div>

</template>

<script>
import {defineComponent} from "vue";
export default defineComponent({
  name:'rightbox',

})
</script>


<style scoped lang="scss">
.c{
  width: 200px;
  height: 500px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
.d{
  position: relative;
  width: 200px;
  height: 90px;
  right: 0;
  transition:.5s;
  overflow: hidden;
}
.d img{
  position: absolute;
  width: 200px;
  transform: translate(0,-70px);
  transition: .5s;
  right: 0;
}
.d dd{
  opacity: 0;
  right: 250px;
}
.d:hover img{
  opacity: 0;
  right: 250px;
}
</style>