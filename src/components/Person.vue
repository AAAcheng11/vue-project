<template>
    <!-- html -->
    <div class="person">
        <h2>一辆{{ car.brand }}汽车，价格是{{ car.price }}万</h2>
        <button @click="changePrice">修改汽车价格</button>
        <hr>
        <ul>
            <li v-for="item in games" :key="item.id">{{ item.name }}</li>
        </ul>
        <button @click="changeFirstGame">修改第一个游戏名字</button>
    </div>
</template>

<script lang="ts" setup name='Person'>
import { reactive } from 'vue';

let car = reactive({ brand: '奔驰', price: 1000 })
let games = reactive([
    { id: 1, name: '王者荣耀' },
    { id: 2, name: '原神' },
    { id: 3, name: '刺激战场' }
])

function changePrice() {
    car.price += 10
}

function changeFirstGame(){
    games[0].name='heiheihei'
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
li {
    font-size: 30px;
}
</style>