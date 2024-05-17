<script setup>
import { ref } from 'vue';
const arreglo = ref(['Tema 1', 'Tema2', 'Tema3'])
const text = ref (['','','',''])
const mostrar = ref(null)

 function mostartexto(index) {
mostrar.value = index;
}
function mostrarholder(index){
return 'Tema del texto : ' + (index+1)
}
</script>
<template>
    <div class="mx-auto w-96 borde-2 px-6 py-4 shadow  bg-blue-300 mt-10">
        <div class="flex flex-col  space-y-2">
            <div class="relative" v-for="(arreglos, index) in arreglo" :key="index">
                <div>
                    <li class=" list-none bg-blue-200  px-4 py-2 flex justify-between"> {{ arreglos }}
                        <button @click="mostartexto(index)">+</button>
                    </li>
                </div>
                <div v-if="mostrar===index" class="bg-blue-50/50 p-2 mt-2 w-full">
                 <input class=" bg-white w-full  h-20 p-2" v-model="text[index]" type="text"  :placeholder="mostrarholder(index)">
                </div>
            </div>
            
        </div>

        
    </div>
</template>