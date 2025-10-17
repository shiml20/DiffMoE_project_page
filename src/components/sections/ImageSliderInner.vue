<script lang="ts" setup>
import { VueCompareImage } from 'vue3-compare-image';

const inputImagePath = './image_inner/line.jpg';
const outputImagePath = './image_inner/real.jpg';
</script>

<template>
  <div>
    <hr class="divider" />

    <div class="section-header">
      <h1 class="section-title">Qualitative Results</h1>
    </div>

    <div class="image-comparison-container">
      <div class="comparison-wrapper">
        <VueCompareImage 
          :left-image="inputImagePath" 
          :right-image="outputImagePath"
          :hover="true"
        />
      </div>
    </div>

  </div>
</template>

<style scoped>
.section-header {
  text-align: center;
}

.image-comparison-container {
  display: flex;
  justify-content: center;
  margin: 0 auto;
  max-width: 800px;
}

.comparison-wrapper {
  margin-top: 20px;
  width: 100%;
}
</style>
