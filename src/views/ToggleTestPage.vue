<template>
  <div class="image-box">
    <div v-if="buttonFlg">
      <img src="@/assets/image/penguin1.jpg" class="image-size"/>
    </div>
    <div v-else>
      <img src="@/assets/image/penguin2.jpg" class="image-size"/>
    </div>
    <SliderToggleBar
     :isOn="buttonFlg"
     on-msg="泳ぎ"
     off-msg="陸上"
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
.image-box {
  margin: 0 auto;
  max-width: 320px;
  height: 300px;
}

.image-size {
  max-width: 320px;
  height: 400px;
}
</style>
