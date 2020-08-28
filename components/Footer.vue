<template>
  <footer class="ph-footer"><slot></slot></footer>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class PhFooter extends Vue {}
</script>

<style lang="scss" scoped>
.ph-footer {
  font-size: 14px;
}
.ph-footer a {
  color: var(--primary-color);
  font-family: 'Lato', sans-serif;
}
.ph-footer a:hover {
  color: var(--primary-color-darker);
}
</style>
