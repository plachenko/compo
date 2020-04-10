<template>
  <div id="capture" ref="capture" />
</template>
<script lang="ts">
import EventBus from '@/EventBus';
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class Grid extends Vue{
  $refs!: {
    capture: HTMLElement;
  }

  mounted(){
    const cap = this.$refs.capture;

    window.addEventListener('resize', (e) => {
      EventBus.$emit('resize');
    });

    cap.addEventListener('pointerdown', (e) => {
      EventBus.$emit('pDn', e);
    });

    cap.addEventListener('pointerup', (e) => {
      EventBus.$emit('pUp', e);
    });

    cap.addEventListener('pointermove', (e) => {
      EventBus.$emit('pMv', e);
    });
  }
}
</script>
<style>
#capture{
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 9998;
  cursor: crosshair;
}

</style>
