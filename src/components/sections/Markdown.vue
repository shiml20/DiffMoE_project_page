<script setup>
import page from '../mds/md.mdx';
</script>

<template>
  <div class="markdown-wrapper">
    <hr class="divider" />

    <div class="section-content">
      <page />
    </div>

  </div>
</template>

<style scoped>
.markdown-wrapper {
  margin: 0;
}

.section-content {
  max-width: 100%;
  margin: 0 auto;
}
</style>