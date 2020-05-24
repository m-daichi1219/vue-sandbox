<template>
  <div>
    <div v-if="buttonFlg">ON</div>
    <div v-else>OFF</div>
    <SliderToggleBar
     :isOn="buttonFlg"
     @toggleClick="buttonFlg = !buttonFlg"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import SliderToggleBar from '@/components/SliderToggleBar.vue';

@Component({
  components: {
    SliderToggleBar,
  },
})
export default class ToggleTestPage extends Vue {
  buttonFlg = true;
}
</script>

<style scoped lang="scss">
.box {
  width: 100px;
  height: 100px;
  background: #000;
  transition: all 300ms 0s ease;
}

.active {
  transform: translateX(300px);
  background: #ff0000;
}
</style>
