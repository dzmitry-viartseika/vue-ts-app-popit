<template>
  <button
    class="btn"
    :class="customBtn"
    @click="handleClickEvent"
    :title="buttonText"
    :disabled="disabled"
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

  @Prop({ type: String, default: 'btn-info' })
  customBtn;

  @Prop({ type: Boolean, default: false })
  disabled;

  handleClickEvent() {
    this.$emit('handleClickEvent');
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

</style>
