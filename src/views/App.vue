<template>
  <div id="comp_disp">
    <Output />
    <Event />
    <Grid />
  </div>
</template>

<script lang="ts">
// @ is an alias to /src
// import Capture from '@/components/Capture.vue';
import Layout from '@/components/Layout.vue';
import Grid from '@/components/Grid.vue';
import ItemBar from '@/components/ItemBar.vue';
import Event from '@/components/Event.vue';
import Output from '@/components/Output.vue';
import { Component, Vue } from 'vue-property-decorator';

@Component({
  name: 'App',
  components: {
    Grid,
    // Capture,
    Event,
    Output,
    Layout,
    ItemBar
  }
})
export default class App extends Vue {
  private itemSelect(e: any){
    console.log('selected', e);
  }

  mounted(){
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
