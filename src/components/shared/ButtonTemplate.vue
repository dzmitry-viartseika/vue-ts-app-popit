<template>
  <button
    class="btn"
    @click="handleClickEvent"
    :title="buttonText"
  >
    {{ buttonText }}
  </button>
</template>

<script lang="ts">
import {
  Vue, Component, Prop,
} from 'vue-property-decorator';

@Component({})
export default class ButtonTemplate extends Vue {
  @Prop({ type: String, required: true })
  buttonText;
  // TODO emit vue component style

  handleClickEvent():void {
    this.$emit('handleClickEvent');
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

</style>
