<template>
  <div class="home">
    <div class="box">
      <div class="box_leftbox">
        <leftbox ></leftbox>
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
import {defineComponent,computed,ref} from "vue";
import {useStore} from 'vuex';
export default defineComponent({
  name: 'HomeView',
  components: {
    rightbox,
    leftbox
  },
  mounted() {
    let b=document.querySelector(".b")
    let d=document.getElementsByClassName("d")
    let time
    let index=0
    let a=function(){
        for(let i=0;i<d.length;i++){
            d[i].className="d"
        }
    }
    let aa= function (){
        a()
        d[index].className="d dd"
    }
    let arr=[
           "static/img/1.d4ed8fb3.jpg",
           "static/img/2.86794d1c.jpg",
           "static/img/3.b2ac04c1.jpg",
           "static/img/4.3c4766d4.jpg",
           "static/img/5.0d3d9045.jpg"
       ]
    function ts(){
        time=setInterval(function (){
            aa()
            index++
            if(index===5){
                index=0
            }
            console.log(index)
            b.style.backgroundImage="url(" +[arr[index]]+ ") "

        },2000)
    }
    for(let i=0;i<d.length;i++){
        d[i].onmousemove=function (){
            b.style.backgroundImage="url(" +[arr[i+1]]+ ") "
            a()
            clearInterval(time)
            index=i+1
            ts()
        }

    }
    ts()
  },
  methods:{

  }

})

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
