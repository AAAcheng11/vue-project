<template>
    <!-- html -->
    <div class="person">
        <h2>姓名：{{ person.name }}</h2>
        <h2>年龄：{{ person.age }}</h2>
        <h2>c1:{{ person.car.c1 }}</h2>
        <h2>c2:{{ person.car.c2 }}</h2>
        <br>
        <button @click="changeNane">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="changeC1">修改第一台车</button>
        <button @click="changeC2">修改第二车</button>
        <button @click="changeCar">修改车</button>
    </div>
</template>

<script lang="ts" setup name='Person'>
import { reactive, watch } from 'vue';

let person = reactive({
    name: '张三',
    age: 18,
    car: {
        c1: 'BMW',
        c2: 'MI'
    }
})


function changeNane() {
    person.name += '#'
}
function changeAge() {
    person.age++
}
function changeC1() {
    person.car.c1 = '宝马'
}
function changeC2() {
    person.car.c2 = '比亚迪'
}
function changeCar() {
    person.car = { c1: '小刀', c2: '大众' }
}
//监视，情况四:监视响应式对象中的某个属性，且该属性时基本类型的，要写成函数式
// watch(() => { return person.name }, () => {
//     console.log('person.name发生变化')
// })

// watch(() => person.car, (a, b) => {
//     console.log('监视', a, b)
// }, { deep: true })

watch([person.car, () => person.name], (a, b) => {
    console.log('监视', a, b)
}, { deep: true })
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