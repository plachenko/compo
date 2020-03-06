<template>
  <div id="capture" ref="capture" />
</template>
<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator';

@Component({})
export default class Item extends Vue{

  $refs!: {
    capture: HTMLElement;
  }

  mounted(){
    this.$refs.capture.addEventListener('pointermove', (e) => {
      this.$emit('pEvt', e);
    })
  }
}
</script>
<style>
#capture{
  height: 100%;
  width: 100%;
  }

</style>