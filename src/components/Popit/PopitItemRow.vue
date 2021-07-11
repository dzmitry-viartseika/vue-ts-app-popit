<template>
  <div class="app-popit__row"
       :style="{'background': customBg}"
  >
    <popit-item-circle
      @togglePopitItem="togglePopitItem"
      :id="popitItem.id"
      :color="popitItem.colorClass"
      :is-clicked="popitItem.isClicked"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import { IPopitItem } from '@/models/models.d';
import PopitItemCircle from '@/components/Popit/PopitItemCircle.vue';

@Component({
  components: {
    PopitItemCircle,
  },
})
export default class PopitItemRow extends Vue {
  @Prop({ required: true })
  popitItem: IPopitItem[];

  get customBg(): string {
    switch (this.popitItem.id) {
      case 1:
      case 2:
      case 3:
      case 4:
      case 5:
      case 6:
        return 'rgba(132, 94, 194, .4)';
      case 7:
      case 8:
      case 9:
      case 10:
      case 11:
      case 12:
        return 'rgba(214, 93, 177, .7)';
      case 13:
      case 14:
      case 15:
      case 16:
      case 17:
      case 18:
        return 'rgba(255, 111, 145, .7)';
      case 19:
      case 20:
      case 21:
      case 22:
      case 23:
      case 24:
        return 'rgba(255, 150, 113, .7)';
      case 25:
      case 26:
      case 27:
      case 28:
      case 29:
      case 30:
        return 'rgba(255, 199, 95, .7)';
      case 31:
      case 32:
      case 33:
      case 34:
      case 35:
      case 36:
        return 'rgba(249, 248, 113, .7)';
      default:
        return 'red';
    }
  }

  togglePopitItem(id: number) {
    this.$emit('togglePopitItem', id);
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

.app-popit__row {
  width: 100px;
  height: 100px;
}
</style>
