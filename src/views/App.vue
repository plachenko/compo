<template>
  <div id="comp_disp">
    <div id="overlay">
      <!-- <capture /> -->
      <!-- <itemBar @itemSelect="itemSelect($event)" /> -->
      <!--
        <div>
          <div v-for="(i, k) in ">
        </div>
      </div>
      <textarea rows="10" v-model="test" />
      -->
    </div>
    <!--
    <div style="position: absolute; overflow: hidden">
      <canvas ref="grid" />
    </div>
    -->
    <!-- <layout /> -->
  </div>
</template>

<script lang="ts">
// @ is an alias to /src
import Capture from '@/components/Capture.vue'
import Layout from '@/components/Layout.vue'
import ItemBar from '@/components/ItemBar.vue'
import { Component, Vue, Watch } from 'vue-property-decorator';

@Component({
  name: 'App',
  components: {
    Capture,
    Layout,
    ItemBar
  }
})
export default class App extends Vue {
  private test = `<template><div></div></template> <style></style>`;
  private itemSelect(e: any){
    console.log('selected', e);
  }

  mounted(){
    this.$nextTick(() => {
      const h = window.innerHeight;
      const w = window.innerWidth;
      const can = this.$refs.grid;
        can.width = w;
        can.height = h;

      const ctx = can.getContext('2d');
      ctx.fillStyle = "#CCC";

      /*
      for(let i = 0; i <= w; i += 10){
        for(let j = 0; j <= h; j += 10){
          ctx.fillRect(i,0,1,h);
          ctx.fillRect(0,j,w,1);
        }
      }
      */
    });

    /*
    for(const i in document.querySelector('#overlay').style){
      console.log(i);
      for(const e of i){
        console.log(i, i[e]);
      }
    }
    */
  }

}
</script>

<style>
#comp_disp{
  display: flex;
  width: 100%;
  height: 100%;
  }
  #overlay{
    z-index: 9999;
    display: flex; 
    flex-flow: column; 
    width: 100%; 
    height: 100%;
    }
</style>
