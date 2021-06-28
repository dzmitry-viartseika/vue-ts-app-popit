<template>
  <div class="app-popit">
    <popit-item-row
      v-for="popitItem in popitItemList"
      :key="popitItem.id"
      :popitItem="popitItem"
      @togglePopitItem="togglePopitItem"
    />
  </div>
</template>

<script lang="ts">
import {
  Vue, Component, Prop, PropSync,
} from 'vue-property-decorator';
import { IPopitItem } from '@/models.d';
import PopitItemRow from '@/components/Popit/PopitItemRow.vue';

// eslint-disable-next-line import/no-unresolved,@typescript-eslint/no-var-requires
const someSoundIn = require('@/assets/audio/popin.mp3');
// eslint-disable-next-line import/no-unresolved,@typescript-eslint/no-var-requires
const someSoundOut = require('@/assets/audio/popout.mp3');

@Component({
  components: {
    PopitItemRow,
  },
})
export default class PopitSection extends Vue {
  @Prop({ required: true })
  popitItemList: IPopitItem[];

  @PropSync('score', { required: true })
  public scoreSynced: number;

  get getSoundIn(): string {
    return someSoundIn;
  }

  get getSoundOut(): string {
    return someSoundOut;
  }

  playSoundIn() {
    const note = new Audio(this.getSoundIn);
    note.addEventListener('canplaythrough', () => {
      note.play();
    });
  }

  playSoundOut() {
    const note = new Audio(this.getSoundOut);
    note.addEventListener('canplaythrough', () => {
      note.play();
    });
  }

  togglePopitItem(id) {
    const currentPopitItem = this.popitItemList.find((item) => item.id === id) as IPopitItem;
    if (currentPopitItem) {
      currentPopitItem.isClicked = !currentPopitItem.isClicked;
      if (currentPopitItem.isClicked) {
        this.playSoundIn();
      } else {
        this.playSoundOut();
      }
      this.scoreSynced += 1;
    }
  }
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
