<template>
  <div id="itemBar">
    <div 
      class="tool" 
      v-for="(tool, k) in tools" 
      @click="$emit('itemSelect', tool)"
      :key="k">{{tool}}</div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class ItemBar extends Vue{
  private tools = [
    'frame',
    'frame',
    'frame',
    'frame',
    'frame',
    'frame',
    'frame',
    'frame',
    'frame',
    'frame',
    'div'
  ];

  mounted(){
    console.log(document.getElementsByTagName('*'));
  }
}
</script>
<style>
#itemBar{
  /* min-width: 300px; */
  width: 100%;
  overflow-x: scroll;
  float: left;
  padding: 10px 0px;
  display: flex;
  flex-wrap: nowrap;
  border-bottom: 2px solid;
  }
  .tool{
    flex-wrap: nowrap;
    float: left;
    padding: 10px 30px;
    user-select: none;
    cursor: pointer;
    margin: 0px 5px;
    background-color:#F00;
    }
</style>