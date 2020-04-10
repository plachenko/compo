<template>
  <div id="layout">
    <div ref='item' class="item"></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import EventBus from '@/EventBus';

@Component({})
export default class Layout extends Vue{

  $refs!: {
    item: HTMLElement;
  }

  mounted(){
    let start = {
      x: 0,
      y: 0
    };

    EventBus.$on('pEvt', (e: any) => {
      if(e.pressure){
        if(start.x && start.y){
          this.$refs.item.style.width = e.offsetX - start.x + "px";
          this.$refs.item.style.height = e.offsetY - start.y + "px";
        }else{
          start = {
            x: e.offsetX,
            y: e.offsetY
          }
        }
      }else{
        if(start.x && start.y){
          start = {x: 0, y: 0 }
        }else{
          this.$refs.item.style.left = e.offsetX + "px";
          this.$refs.item.style.top = e.offsetY + "px";
        }
      }
    })
  }
}
</script>
<style>
.item{
  width: 100px;
  height: 100px;
  position: absolute;
  background-color:#F00;
  /* border: 1px solid; */
}
#layout{
  flex: 1;
  height: 100%;
  width: 100%;
}
</style>
