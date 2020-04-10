<template>
  <textarea ref="output" v-model="output" />
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class Item extends Vue{
  private output = "";

  $refs!: {
    output: HTMLTextAreaElement;
  }

  mounted(){
    this.output = "test!";
  }
}
</script>
<style scoped>
textarea{
  height: 90%;
  width: 40%;
  z-index: 9999;
  position: absolute;
}
</style>
