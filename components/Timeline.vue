<template>
  <transition name="ph-fade">
    <div v-show="show" class="ph-timeline">
      <slot></slot>
    </div>
  </transition>
</template>

<script lang="ts">
import { Prop, Component, Vue } from 'vue-property-decorator'

@Component
export default class PhTimeline extends Vue {
  @Prop() readonly option!: string
  @Prop({ default: false }) readonly firstLetter!: Boolean

  show = false

  mounted() {
    this.$parent.$on('timeline-change', (eventOption: String) => {
      this.show = eventOption === this.option
    })
  }
}
</script>

<style lang="scss" scoped>
.ph-fade-enter-active {
  order: -10;
}
.ph-fade-leave-active {
  order: 10;
}
.ph-fade-enter-active,
.ph-fade-leave-active {
  transition: opacity 0.2s, transform 0.2s;
}
.ph-fade-enter,
.ph-fade-leave-to {
  transform: translate3d(0, 2rem, 0);
  opacity: 0;
}
.ph-fade-leave,
.ph-fade-enter-to {
  transform: translate3d(0, 0, 0);
  z-index: 10;
}
</style>
