<template>
  <div class="app">
    <div class="app-container">
      <popit-section
        :popitItemList="popitItemList"
        :score.sync="score"
      />
      <div class="app-navigation">
        <button-template
          :button-text="'Reset'"
          :custom-btn="'btn-warning'"
          @handleClickEvent="handleClickEvent"
        />
        <div>Score: {{ score }}</div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import PopitSection from '@/components/Popit/PopitSection.vue';
import ButtonTemplate from '@/components/shared/ButtonTemplate.vue';
import { PopitItemList } from '@/models/extensions/PopitItemList';
// eslint-disable-next-line import/no-unresolved,@typescript-eslint/no-var-requires
const someSoundOut = require('@/assets/audio/popout.mp3');

const popitListItems = new PopitItemList();

@Component({
  components: {
    PopitSection,
    ButtonTemplate,
  },
})
export default class App extends Vue {
  popitItemList = popitListItems.items;

  score = 0;

  get getSoundOut(): string {
    return someSoundOut;
  }

  handleClickEvent(): void {
    this.score = 0;
    this.resetScore();
  }

  playSoundOut() {
    const note = new Audio(this.getSoundOut);
    note.addEventListener('canplaythrough', () => {
      note.play();
    });
  }

  resetScore(): void {
    this.score = 0;
    this.playSoundOut();
    this.popitItemList.forEach((item) => {
      if (item.isClicked) {
        // eslint-disable-next-line no-param-reassign
        item.isClicked = false;
      }
      return item;
    });
  }
}

</script>

<style lang="scss">
@import '@/assets/scss/style.scss';

.app {
  padding: 20px;
  &-navigation {
    display: flex;
    justify-content: space-between;
  }
}

</style>
