<template>
  <div class="layout-footer">
    <slot />
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';

@Component()
export default class FooterMenu extends Vue {
}
</script>

<style scoped lang="scss">
.layout-footer {
  position: fixed;
  display: flex;
  bottom: 0;
  width: 100%;
  height: 3rem;
  background: rgba(0, 0, 255, 0.5);
}
</style>
