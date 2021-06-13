<template>
  <div class="app">
    <div class="app-container">
      <PopitSection :popitItemList="popitItemList"/>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import PopitSection from '@/components/Popit/PopitSection.vue';
import { IPopitItem } from '@/models.d';

@Component({
  components: {
    PopitSection,
  },
})
export default class App extends Vue {
  popitItemList: IPopitItem[] = [
    {
      id: 1,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 2,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 3,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 4,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 5,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 6,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 7,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 8,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 9,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 10,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 11,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 12,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 13,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 14,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 15,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 16,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 17,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 18,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 19,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 20,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 21,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 22,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 23,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 24,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 25,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 26,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 27,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 28,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 29,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 30,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 31,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 32,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 33,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 34,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 35,
      isClicked: false,
      colorClass: 'orange',
    },
    {
      id: 36,
      isClicked: false,
      colorClass: 'orange',
    },
  ]
}

</script>

<style lang="scss">
@import '@/assets/scss/style.scss';

</style>
