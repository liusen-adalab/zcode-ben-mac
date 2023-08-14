<template>
    <!-- <FileNode v-for="file in files" :name="file.name" :isDir="file.isDir"></FileNode> -->
    <FileCsdn v-for="file in files" :name="file.name" :isDir="file.isDir" :lastModified="file.lastModified"></FileCsdn>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
// import { File } from '../components/FileNode.vue'
// import FileNode from "../components/FileNode.vue"
import FileCsdn from "../components/FileCsdn.vue"
import { File } from '../components/FileCsdn.vue';

// interface FileNode {
//     isDir: boolean
//     name: string
// }

const files = ref<File[]>()
files.value = [{ isDir: true, name: "aa", lastModified: "2020-08-03" }, { isDir: false, name: "bb", lastModified: "2031-02-08" }]


</script>