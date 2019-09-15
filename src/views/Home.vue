<template>
  <div class="home">
      <button @click="BtnCLick" >点击</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
  data(){
    return {
      promise:""
    }
  },
  methods:{
    BtnCLick(){
       let promise = navigator.mediaDevices.getUserMedia({
            video: {width: 500, height: 500},
            audio: true
        });
        this.promise = promise;
        this.$router.push({
          name:"about",
          path:"/about",
          params:{
            msg:this.promise
          }
        })
        
    }
  }
}
</script>
