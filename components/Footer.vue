<template>
  <footer class="ph-footer"><slot></slot></footer>
</template>
<style>
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
