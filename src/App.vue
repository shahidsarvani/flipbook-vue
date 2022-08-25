<template>
  <div id="app">
    <!-- <button @click="changePage">1</button> -->
    <Flipbook
      ref="flipbook"
      class="flipbook"
      :pages="pages"
      :zooms="null"
      :nPolygons="20"
      @flip-right-start="onFlipRightStart"
    >
      <!-- <div class="next-prev-btn">
        <button class="prev-btn" @click="flipbook.flipLeft">
          Previous Page
        </button>
        <button class="next-btn" @click="flipbook.flipRight">Next Page</button>
      </div>
       <p>{{ flipbook }}</p> 
      <p @click="flipbook.page = 1">1</p>
      {{ flipbook.numPages }}-->
    </Flipbook>
  </div>
</template>

<script>
import Flipbook from "flipbook-vue";

export default {
  name: "App",
  components: {
    Flipbook,
  },
  methods: {
    // changePage() {
    //   this.$refs.flipbook.frontImage = this.$refs.flipbook.pageUrl(7);
    //   this.$refs.flipbook.backImge = this.$refs.flipbook.pageUrl(8);
    //   this.$refs.flipbook.firstPage = 7;
    //   this.$refs.flipbook.secondPage = 8;

    //   // this.$refs.flipbook.flipAuto(true);
    // },
    onFlipRightStart(page) {
      console.log(page);
    },
  },
  data() {
    return {
      singlePage: true,
      pages: [
        null,
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/1.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/2_2.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/2_1.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/3_2.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/3_1.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/4_2.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/4_1.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/5_2.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/5_1.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/6_2.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/6_1.jpg",
        "https://digitalpoint.ae/dev/flipbook-demo/2/images_new/7_2.jpg",
      ],
    };
  },
};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  display: flex;
  flex-direction: row;
  align-items: center;
  background-color: #333;
  color: #ccc;
  overflow: hidden;
}
a {
  color: inherit;
}
.action-bar {
  width: 100%;
  height: 30px;
  padding: 10px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.action-bar .btn {
  font-size: 30px;
  color: #999;
}
.action-bar .btn svg {
  bottom: 0;
}
.action-bar .btn:not(:first-child) {
  margin-left: 10px;
}
.has-mouse .action-bar .btn:hover {
  color: #ccc;
  filter: drop-shadow(1px 1px 5px #000);
  cursor: pointer;
}
.action-bar .btn:active {
  filter: none !important;
}
.action-bar .btn.disabled {
  color: #666;
  pointer-events: none;
}
.action-bar .page-num {
  font-size: 12px;
  margin-left: 10px;
}
.flipbook {
  margin: 0 auto;
} 
.flipbook .viewport {
  width: 90vw !important;
  height: calc(100vh - 50px - 40px) !important;
}
.flipbook .bounding-box {
  box-shadow: 0 0 20px #000;
}
.credit {
  font-size: 12px;
  line-height: 20px;
  margin: 10px;
}
</style>
