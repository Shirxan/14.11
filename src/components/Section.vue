<template>
  <div class="container d-flex">
    <h1>Player:{{ count }}</h1>
    <h2 class="offset-3">Wolf:{{ count1 }}</h2>
  </div>
  <div class="btn-group" role="group" aria-label="Default button group">
    <button id="hucum" @click="hucum()" type="button" class="btn btn-outline-dark">
      Hücüm
    </button>
    <button id="qetihucum" @click="qetihucum()" type="button" class="btn btn-outline-dark">
      Şiddətli hücüm
    </button>
    <button @click="son()" type="button" class="btn btn-outline-dark">Son</button>
  </div>

</template>


<script>
export default {
  data() {
    return {
      count: 100,
      count1: 100,
      point : 0,
      point1 :0 
    };
  },
  methods: {
    hucum() {
      if (this.count>0) {
        this.count-=10
        this.point1+= 1
      } else {
        this.count = 0;
      }
    },
    qetihucum(){
      if(this.count1>0 ){
      this.count1-=25
      this.point+=1
    }else if(this.count1>0){
     this.count1=0
    }
    },
    son(){
      location.reload()
    }
  },
  watch:{
    point(){
      if(this.point==2){
        document.querySelector('#qetihucum').setAttribute("class","btn disabled")
      }
    },
    point1(){
      if(this.point1==7){
        document.querySelector('#hucum').setAttribute("class","btn disabled")
      }
    }
  }
};
</script>

<style scoped>
.btn-group {
  margin-left: 223px;
  margin-top: 40px;
}
</style>
