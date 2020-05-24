<template>
  <div class="layout-button"
    @click="$emit('toggleClick')"
    :class="{'background-button': 'background-button', 'on': isOn}" />
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class SliderToggleBar extends Vue {
  @Prop({ default: false })
  isOn!: boolean;

  get btnClass() {
    return [
      'layout-button',
      'background-button',
      this.isOn ? 'on' : '',
    ];
  }
}
</script>

<style scoped lang="scss">
.layout-button {
  width: 100%;
  height: 1.5rem;
  border: none;
}

.background-button {
  background: linear-gradient(135deg, #f0bc68 0%, #f0bc68 70%, #c4d7d1 50%, #c4d7d1 100%);
  -webkit-transition: all 1s ease 1s;
  transition: all 1s ease 1s;
  cursor: pointer;
  &.on {
    background: linear-gradient(45deg, #f0bc68 0%, #f0bc68 30%, #c4d7d1 30%, #c4d7d1 100%);
    // transition: all 300ms 0s ease;
  }
}

</style>
