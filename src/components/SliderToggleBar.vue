<template>
  <div class="layout-button"
    @click="$emit('toggleClick')"
    :class="{'background-button': 'background-button', 'on': isOn}">
    <span class="on-message-text">{{onMsg}}</span>
    <span class="off-message-text">{{offMsg}}</span>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class SliderToggleBar extends Vue {
  @Prop({ default: false })
  isOn!: boolean;

  @Prop({ default: 'ON' })
  onMsg!: string;

  @Prop({ default: 'OFF' })
  offMsg!: string;

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
  position: relative;
}

.background-button {
  background: linear-gradient(135deg, #f0bc68 0%, #f0bc68 70%, #c4d7d1 50%, #c4d7d1 100%);
  -webkit-transition: all 1s ease 1s;
  transition: all 1s ease 1s;
  cursor: pointer;
  &.on {
    background: linear-gradient(45deg, #f0bc68 0%, #f0bc68 30%, #c4d7d1 30%, #c4d7d1 100%);
  }
}

.on-message-text {
  display: inline;
  position: absolute;
  top: 50%;
  left: 5%;
  transform: translateY(-50%);
  font-weight: bold;
}

.off-message-text {
  display: inline;
  position: absolute;
  top: 50%;
  right: 5%;
  transform: translateY(-50%);
  font-weight: bold;
}

</style>
