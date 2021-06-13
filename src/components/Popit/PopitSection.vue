<template>
  <div class="app-popit">
    <popit-item-row
      v-for="popitItem in popitItemList"
      :key="popitItem.id"
      :popitItem="popitItem"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import { IPopitItem } from '@/models.d';
import PopitItemRow from '@/components/Popit/PopitItemRow.vue';

@Component({
  components: {
    PopitItemRow,
  },
})
export default class PopitSection extends Vue {
  @Prop({ required: true })
  popitItemList: IPopitItem[];
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variables";

.app-popit {
  width: 100%;
  max-width: 600px;
  border-radius: $borderRadiusLarge;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  box-shadow: 0 4px 42px -3px $boxShadowPopitColor;
  display: flex;
  flex-wrap: wrap;
}

.orange {
  background: #eeaeca;
}
</style>
