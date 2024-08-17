<template>
    <!-- html -->
    <div class="person">
        <h2>姓名：{{ person.name }}</h2>
        <h2>年龄：{{ person.age }}</h2>
        <button @click="changName">修改名字</button>
        <button @click="changAge">修改年龄</button>
        <button @click="changePerson">修改</button>
    </div>
</template>

<script lang="ts" setup name='Person'>
import { reactive, watch } from 'vue';
// 数据求和
let person = reactive({
    name: '张三',
    age: 18
})
function changName() {
    person.name += '#'
}

function changAge() {
    person.age += 2
}

function changePerson() {
    Object.assign(person, { name: 'lisi', age: 19 })
}

watch(person, (newValue, oldValue) => {
    console.log('person变化了', newValue, oldValue)
})

</script>



<style>
/* css */
.person {
    background-color: skyblue;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}

button {
    margin: 0 5px;
}

li {
    font-size: 30px;
}
</style>