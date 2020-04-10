<template>
  <div id="capture" ref="capture" />
</template>
<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator';
// import { EventBus } from '@/eventbus.ts';

@Component({})
export default class Capture extends Vue{

  $refs!: {
    capture: HTMLElement;
  }

  mounted(){
    this.$refs.capture.addEventListener('pointermove', (e) => {
      EventBus.$emit('pEvt', e);
    })
  }
}
</script>
<style>
#capture{
  z-index: 9998;
  flex: 1;
  }
</style>
