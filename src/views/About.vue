<template>
  <div class="about">
    <router-link to="/about">about</router-link>
    <router-view></router-view>
    <video ></video>
    <button @click="BtnClickZ">拍照</button>
    <canvas></canvas>
  </div>
</template>

<script>
export default {
  name:"about",
  data(){
    return {

    }
  },
  mounted(){
    let promise = this.$route.params.msg
    // let video = this.$el.lastElementChild;
    let video = this.$el.children[1]
    promise.then(function (MediaStream) {
            video.srcObject = MediaStream;
            video.play();
    })
  },
  methods:{
    BtnClickZ(){
      let canvas = this.$el.children[3];
      let video = this.$el.children[1]
      canvas.height = 800
      canvas.width = 600
      let ctx = canvas.getContext('2d');
      ctx.drawImage(video,0,0, 700, 800);

    }
  }
}
</script>
<style  scoped>
  
</style>