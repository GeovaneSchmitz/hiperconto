<template>
  <div class="ph-question-wrapper">
    <div class="ph-question-selector">
      <div class="ph-question"><slot name="question"></slot></div>
      <div class="ph-question-buttons"><slot name="buttons"></slot></div>
    </div>
    <div class="ph-question-timeline">
      <slot name="timeline"></slot>
    </div>
  </div>
</template>
<script>
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class PhQuestion extends Vue {
  mounted() {
    this.$children.map((child) =>
      child.$on('click', (option) => {
        this.$emit('timeline-change', option)
      })
    )
  }
}
</script>

<style lang="scss" scoped>
.ph-question {
  z-index: 10;
  color: var(--primary-color);
  font-size: 24px;
  font-family: Lato, sans-serif;
  font-weight: 700;
  text-align: center;
}
.ph-question-selector {
  background-color: var(--highlight-color);
  box-shadow: 0 1rem 20px var(--box-shadow-color);
  margin: 2rem 0;
  padding: 1rem;
  border-radius: 5px;
}
.ph-question-timeline {
  display: flex;
  flex-direction: column;
}
.ph-question-buttons {
  display: flex;
  justify-content: space-around;
  margin-top: 1rem;
}
</style>
