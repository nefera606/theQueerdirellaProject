<template>
    <div class="fullpage-container">
      <div class="fullpage-wp" v-fullpage="opts" ref="example">
        <div class="page-1 page">
          <p class="part-1" v-animate="{value: 'bounceInLeft'}">fullpage-vue</p>
        </div>
        <div class="page-2 page">
          <p class="part-2" v-animate="{value: 'bounceInRight'}">fullpage-vue</p>
        </div>
        <div class="page-3 page">
          <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
          <p class="part-3" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
          <p class="part-3" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
        </div>
      </div>
      <button @click="moveNext">next</button>
    </div>
</template>

<script>
export default {
  data() {
    return {
      opts: {
        start: 0,
        dir: 'v',
        duration: 500,
        beforeChange: function (currentSlideEl,currenIndex,nextIndex) {
        },
        afterChange: function (currentSlideEl,currenIndex) {
        }
      }
    }
  },
  methods:{
    moveNext(){
      this.$refs.example.$fullpage.moveNext(); //Move to the next page
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.fullpage-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
</style>

