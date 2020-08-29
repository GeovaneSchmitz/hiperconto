<template>
  <div class="ph-authors">
    <div class="ph-author-label">
      {{ $t('authorLabel') }}
    </div>
    <div v-for="(item, index) in authors" :key="index" class="ph-author">
      {{ item }}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class PhAuthors extends Vue {
  authors = [
    this.$t('authorGeovane'),
    this.$t('authorPamela'),
    this.$t('authorValter'),
  ]
}
</script>

<style lang="scss" scoped>
.ph-authors {
  color: var(--text-color-secundary);
  display: block;
  font-size: 10px;
  font-family: 'Lato', sans-serif;
  margin: 0.5rem 0 3rem 0;
}

.ph-author,
.ph-author-label {
  font-family: 'Lato', sans-serif;
}
.ph-author-label {
  font-size: 12px;
}
</style>
