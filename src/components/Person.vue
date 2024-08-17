<template>
    <!-- html -->
    <div class="person">
        <h2>当前求和：{{ sum }}</h2>
        <button @click="changeSum">++++++++</button>
    </div>
</template>

<script lang="ts" setup name='Person'>
import { ref, watch } from 'vue';
// 数据求和
let sum = ref(0)

function changeSum() {
    sum.value += 5
}

let stopWatch = watch(sum, (newValue, oldValue) => {
    console.log(newValue, oldValue)
    console.log('sum变化了')
    if (newValue > 20) {
        stopWatch()
    }
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