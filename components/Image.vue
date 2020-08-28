<template>
  <div class="ph-image">
    <div class="ph-image-wrapper">
      <img class="ph-image-img" :src="src" />
    </div>
    <div class="ph-image-description">{{ discription }}</div>
  </div>
</template>
<script>
import Vue from 'vue'
export default Vue.extend({
  props: {
    src: {
      type: String,
      required: true,
    },
    discription: {
      type: String,
      default: '',
    },
  },
})
</script>
<style scoped>
.ph-image {
  display: flex;
  flex-direction: column;
  width: calc(100% + 4rem);
  margin: 0 -2rem;
}
.ph-image-wrapper {
  overflow: hidden;
  max-height: 600px;
}
.ph-image-description {
  margin: 0.5rem 0 2rem 0;
  color: #333;
  font-size: 14px;
  font-family: 'Lato', sans-serif;
  text-align: center;
}
.ph-image-img {
  max-width: 110%;
  object-fit: cover;
  width: auto;
  height: auto;
}
</style>
