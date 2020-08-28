<template>
  <div>
    <div class="ph-title">
      {{ $t('title') }}
    </div>
    <div class="ph-subtitle">
      {{ $t('subtitle') }}
    </div>
  </div>
</template>
<style scoped>
.ph-title {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1;
  margin-top: 2rem;
  color: var(--primary-color);
}

.ph-subtitle {
  margin: 0 0 4rem 0;
  line-height: 1;
  font-weight: 400;
  color: #444;
  font-family: 'Lato', sans-serif;
}
</style>
