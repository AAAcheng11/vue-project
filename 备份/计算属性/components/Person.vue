<template>
    <!-- html -->
    <div class="person">
        姓：<input type="text" v-model="firstName">
        <br>
        名：<input type="text" v-model="lastName">
        <br>
        全名：<span>{{ fullName }}</span>
        <button @click="changeFullName">修改全名</button>
    </div>
</template>

<script lang="ts" setup name='Person'>
import { ref, computed } from 'vue';

let firstName = ref('张')
let lastName = ref('三')

//计算属性是只读的
// let fullName = computed(() => {
//     return firstName.value + lastName.value
// })
let fullName = computed({
    get(){
        return firstName.value + lastName.value
    },
    set(val){
        const [str1,str2] = val.split('-')
        console.log(str1)
        console.log(str2)
        firstName.value = str1
        lastName.value = str2
    }
})
function changeFullName() {
    fullName.value = 'li-si'
}


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