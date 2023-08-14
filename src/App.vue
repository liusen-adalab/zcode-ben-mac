<script setup lang="ts">
import Files from './components/Files.vue';
import FileNode from './components/FileNode.vue';
import FileManager from './views/FileManager.vue'
</script>

<template>
  <Files></Files>
  <FileNode></FileNode>
  <FileManager></FileManager>
</template>

<style scoped>
.logo.vite:hover {
  filter: drop-shadow(0 0 2em #747bff);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #249b73);
}
</style>
