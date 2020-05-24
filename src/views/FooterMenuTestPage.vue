<template>
  <div class="container">
    <template v-if="isShowBox">
      <div v-for="c in count" :key="c" class="box">
      </div>
      <button @click="addCount">Add</button>
    </template>
    <template v-if="!isShowBox">
      <h1>tooltips page</h1>
    </template>
    <FooterMenu>
      <div class="layout-footer-button" @click="isShowBox = true">BOX</div>
      <div class="layout-footer-button" @click="isShowBox = false">tooltips</div>
    </FooterMenu>
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';
import FooterMenu from '@/components/FooterMenu.vue';

@Component({
  components: {
    FooterMenu,
  },
})
export default class FooterMenuTestPage extends Vue {
  count = 2

  isShowBox = true

  addCount() {
    this.count += 1;
  }
}
</script>

<style scoped lang="scss">
.container {
  padding-bottom: 50px;
}

.box {
  height: 100px;
  border: 1px black solid;
  margin: 5px;
}

.layout-footer-button {
  display: inline-block;
  border: 1px black solid;
  margin: 5px;
  height: 80%;
  width: 100%;
}

.layout-footer-button:hover {
  background: rgba(255, 255, 255, 0.5)
}
</style>
