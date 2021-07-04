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
import { IPopitItem } from '@/models.d';
// eslint-disable-next-line import/no-unresolved,@typescript-eslint/no-var-requires
const someSoundOut = require('@/assets/audio/popout.mp3');

@Component({
  components: {
    PopitSection,
    ButtonTemplate,
  },
})
export default class App extends Vue {
  popitItemList: IPopitItem[] = [
    {
      id: 1,
      isClicked: false,
      colorClass: '#C4FCEF',
    },
    {
      id: 2,
      isClicked: false,
      colorClass: '#C4FCEF',
    },
    {
      id: 3,
      isClicked: false,
      colorClass: '#C4FCEF',
    },
    {
      id: 4,
      isClicked: false,
      colorClass: '#C4FCEF',
    },
    {
      id: 5,
      isClicked: false,
      colorClass: '#C4FCEF',
    },
    {
      id: 6,
      isClicked: false,
      colorClass: '#C4FCEF',
    },
    {
      id: 7,
      isClicked: false,
      colorClass: '#D65DB1',
    },
    {
      id: 8,
      isClicked: false,
      colorClass: '#D65DB1',
    },
    {
      id: 9,
      isClicked: false,
      colorClass: '#D65DB1',
    },
    {
      id: 10,
      isClicked: false,
      colorClass: '#D65DB1',
    },
    {
      id: 11,
      isClicked: false,
      colorClass: '#D65DB1',
    },
    {
      id: 12,
      isClicked: false,
      colorClass: '#D65DB1',
    },
    {
      id: 13,
      isClicked: false,
      colorClass: '#FF6F91',
    },
    {
      id: 14,
      isClicked: false,
      colorClass: '#FF6F91',
    },
    {
      id: 15,
      isClicked: false,
      colorClass: '#FF6F91',
    },
    {
      id: 16,
      isClicked: false,
      colorClass: '#FF6F91',
    },
    {
      id: 17,
      isClicked: false,
      colorClass: '#FF6F91',
    },
    {
      id: 18,
      isClicked: false,
      colorClass: '#FF6F91',
    },
    {
      id: 19,
      isClicked: false,
      colorClass: '#FF9671',
    },
    {
      id: 20,
      isClicked: false,
      colorClass: '#FF9671',
    },
    {
      id: 21,
      isClicked: false,
      colorClass: '#FF9671',
    },
    {
      id: 22,
      isClicked: false,
      colorClass: '#FF9671',
    },
    {
      id: 23,
      isClicked: false,
      colorClass: '#FF9671',
    },
    {
      id: 24,
      isClicked: false,
      colorClass: '#FF9671',
    },
    {
      id: 25,
      isClicked: false,
      colorClass: '#FFC75F',
    },
    {
      id: 26,
      isClicked: false,
      colorClass: '#FFC75F',
    },
    {
      id: 27,
      isClicked: false,
      colorClass: '#FFC75F',
    },
    {
      id: 28,
      isClicked: false,
      colorClass: '#FFC75F',
    },
    {
      id: 29,
      isClicked: false,
      colorClass: '#FFC75F',
    },
    {
      id: 30,
      isClicked: false,
      colorClass: '#FFC75F',
    },
    {
      id: 31,
      isClicked: false,
      colorClass: '#F9F871',
    },
    {
      id: 32,
      isClicked: false,
      colorClass: '#F9F871',
    },
    {
      id: 33,
      isClicked: false,
      colorClass: '#F9F871',
    },
    {
      id: 34,
      isClicked: false,
      colorClass: '#F9F871',
    },
    {
      id: 35,
      isClicked: false,
      colorClass: '#F9F871',
    },
    {
      id: 36,
      isClicked: false,
      colorClass: '#F9F871',
    },
  ];

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
