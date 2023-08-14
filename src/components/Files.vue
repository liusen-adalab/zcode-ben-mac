<template>
    <div draggable="true" class="dragdiv file" @dragstart="dragStart" @select="onSelect">拖动我</div>

    <div @dragover="fileHover" :class="folderHoverClass" @dragleave="dragleave" @drop="onDrop" class="dir">
        folder
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const folderHoverClass = ref({
    fileshover: false
})

function onSelect(e: Event) {
    console.log("seleted", e)
}

function dragStart(event: DragEvent) {
    console.log("start", event)
    event.dataTransfer?.setData("name", "value")
}

function fileHover(event: DragEvent) {
    console.log("hover", event)
    event.preventDefault()

    folderHoverClass.value.fileshover = true
}

function onDrop(event: DragEvent) {
    const data = event.dataTransfer?.getData('name'); // 获取文件的数据
    folderHoverClass.value.fileshover = false
    console.log(data)
}

function dragleave(event: Event) {
    console.log("leave ", event)
    console.log("vue class")
    folderHoverClass.value.fileshover = false
}


// 添加dragleave事件处理程序，离开可放置区域触发

// files.addEventListener('dragleave', (event) => {


// });

</script>

<style>
.fileshover {
    background-color: rgba(0, 255, 255, 0.979);
}

.file {
    width: 100px;
    height: 100px;
    border-width: 1px;
    border-color: aqua;
    border-style: solid;
    margin: 20px;
}

.dir {
    width: 100px;
    height: 100px;
    border-width: 1px;
    border-style: solid;
    border-color: antiquewhite;
    margin: 20px;
}
</style>