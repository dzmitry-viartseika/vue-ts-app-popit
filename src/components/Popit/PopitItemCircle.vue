<template>
  <div class="app-popit__circle"
       :class="{colorClass}"
       @click="togglePopitItem"
  >
    {{ id }}
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component({})
export default class PopitItemCircle extends Vue {
  @Prop({ type: Number, required: true })
  id: number;

  @Prop({ type: String })
  colorClass: string;

  togglePopitItem(): void {
    this.$emit('togglePopitItem', this.id);
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";
.app-popit__circle {
  border-radius: 50%;
  border: 4px solid black;
  height: 100%;
}

.app-popit__item_clicked {
  background: green;
}

.checked {
  filter: brightness(0.8);
}
</style>
