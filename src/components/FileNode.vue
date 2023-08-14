<template>
    <div>
        <el-icon :size="50" v-if="props.isDir">
            <Document />
        </el-icon>
        <el-icon :size="50" v-else>
            <Folder />
        </el-icon>
        <span>{{ props.name }}</span>
    </div>
    <div>

    </div>
</template>

<script lang="ts" setup>
export interface File {
    name: string,
    isDir: boolean
    lastModified: string
}

const props = withDefaults(defineProps<File>(), { name: "unknown", isDir: false })


</script>