<template>
  <div :class="{ 'ph-text-with-first-letter': firstLetter }">
    <p v-for="item in text" :key="item" class="ph-paragraph">
      <span class="ph-first-letter">{{ item.charAt(0) }}</span
      >{{ item.substring(1) }}
    </p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    text: {
      type: Array,
      required: true,
    },
    firstLetter: {
      type: Boolean,
      default: false,
    },
  },
})
</script>
<style scoped>
.ph-paragraph {
  line-height: 1.5;
  text-align: justify;
  text-justify: inter-word;
  color: rgba(0, 0, 0, 0.9);
  font-size: 14px;
}

.ph-text-with-first-letter > p:first-child > .ph-first-letter {
  font-size: 42px;
  line-height: 4px;
  margin-right: 3px;
  vertical-align: middle;
  float: left;
  color: var(--primary-color);
}

:not(.ph-text-with-first-letter) > p.ph-paragraph,
.ph-text-with-first-letter > p.ph-paragraph:not(:first-child) {
  text-indent: 1cm;
}
</style>
