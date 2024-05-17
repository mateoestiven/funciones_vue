<script setup>
import { ref } from 'vue'

const data = ['Tema1','Tema2','Tema3','Tema4']

const selectIndex = ref(0)

function showInfo(i){
    if(i == selectIndex.value){
        selectIndex.value = -1
    }else{
        selectIndex.value = i
    }
    
}
</script>

<template>
    <div class="bg-blue-600 p-2 max-w-60 mx-auto mt-12">
        <div
        v-for="(theme, i) in data"
        :key="i"
        >

            <h1 @click="showInfo(i)"
            class="select-none hover:cursor-pointer bg-blue-400 text-white px-1 flex justify-between"
            :class="{'bg-blue-800': selectIndex == i}"
            >
               {{ theme }} 
                <span>
                    {{ selectIndex == i ? '-' : '+' }}
                </span>
            </h1>
            <div v-show="selectIndex == i"
            class="bg-blue-50/50 p-1">
                Texto del tema 1
            </div>
        </div>
       
    </div>
</template>