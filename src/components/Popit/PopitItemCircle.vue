<template>
  <div class="app-popit__circle"
       :style="[(isClicked) ? {'background': color} : '', {'borderColor': color}]"
       @click="togglePopitItem"
  >
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component({})
export default class PopitItemCircle extends Vue {
  @Prop({ type: Number, required: true })
  id: number;

  @Prop({ type: String })
  color: string;

  @Prop({ type: Boolean, default: false })
  isClicked;

  togglePopitItem(): void {
    this.$emit('togglePopitItem', this.id);
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

.app-popit__circle {
  border-radius: 50%;
  border: 4px solid transparent;
  height: 100%;
  cursor: pointer;
  transition: opacity .15s ease-in;

  &:hover {
    opacity: .8;
  }
}
</style>
