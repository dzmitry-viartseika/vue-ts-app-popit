<template>
  <div class="app-popit__row">
    <popit-item-circle
      @togglePopitItem="togglePopitItem"
      :id="popitItem.id"
      :color="popitItem.colorClass"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import { IPopitItem } from '@/models.d';
import PopitItemCircle from '@/components/Popit/PopitItemCircle.vue';

@Component({
  components: {
    PopitItemCircle,
  },
})
export default class PopitItemRow extends Vue {
  @Prop({ required: true })
  popitItem: IPopitItem[];

  togglePopitItem(id) {
    this.$emit('togglePopitItem', id);
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

.app-popit__row {
  background: red;
  width: 100px;
  height: 100px;
}
</style>
