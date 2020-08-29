<template>
  <div :class="{ 'ph-text-with-first-letter': firstLetter }">
    <p v-for="(item, index) in text" :key="item" class="ph-paragraph">
      <span v-if="firstLetter && index === 0" class="ph-first-letter">{{
        item.charAt(0)
      }}</span
      >{{ firstLetter && index === 0 ? item.substring(1) : item }}
    </p>
  </div>
</template>

<script lang="ts">
import { Prop, Component, Vue } from 'vue-property-decorator'

@Component
export default class PhText extends Vue {
  @Prop() readonly text!: string[]
  @Prop({ default: false }) readonly firstLetter!: Boolean
}
</script>

<style lang="scss" scoped>
.ph-paragraph {
  line-height: 1.5;
  text-align: justify;
  text-justify: inter-word;
  color: var(--text-color);
  font-size: 14px;
}

.ph-first-letter {
  font-size: 42px;
  line-height: 1;
  margin-right: 4px;
  vertical-align: bottom;
  float: left;
  color: var(--primary-color);
}

:not(.ph-text-with-first-letter) > p.ph-paragraph,
.ph-text-with-first-letter > p.ph-paragraph:not(:first-child) {
  text-indent: 1cm;
}
</style>
