<template>
  <div>
    <div v-if="buttonFlg" class="image-box">
      <img src="@/assets/image/penguin1.jpg" class="image-size"/>
    </div>
    <div v-else class="image-box">
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
  width: 100%;
  height: 300px;
}

.image-size {
  width: 100%;
}
</style>
