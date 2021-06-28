<template>
  <div class="app-popit__circle"
       :style="(isClicked) ? {'background': color} : ''"
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

  isClicked = false;

  togglePopitItem(): void {
    this.$emit('togglePopitItem', this.id);
    this.isClicked = !this.isClicked;
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

.app-popit__circle {
  border-radius: 50%;
  border: 2px solid black;
  height: 100%;
  cursor: pointer;
  transition: opacity .15s ease-in;

  &:hover {
    opacity: .8;
  }
}

.checked {
  filter: brightness(0.8);
}
</style>
