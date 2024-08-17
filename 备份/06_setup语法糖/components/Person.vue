<template>
    <!-- html -->
    <div class="person">
        <h2>姓名：{{ name }}</h2>
        <h2>年龄：{{ age }}</h2>
        <button @click="updateName">修改名字</button>
        <button @click="updateAge">修改年龄</button>
        <button @click="showTle">查看联系方式</button>
    </div>
</template>

<!-- <script lang="ts">
export default {
    name: 'Person'
}
</script> -->
<script lang="ts" setup name='Person12'>
let name = "张三"
let age = 18
let tel = 18214283087
function updateName() {
    name = 'zhang-san'
}
function updateAge() {
    age++
}
function showTle() {
    alert(tel)
}
</script>

<style>
/* css */
.person {
    background-color: #fff;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}

button {
    margin: 0 5px;
}
</style>