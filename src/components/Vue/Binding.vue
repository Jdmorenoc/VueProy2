<script setup>
    import { ref, computed } from 'vue'
    const text = ref(" Hola mundo ")
    const checked = ref(true)

    const items = ["Hola", "mundo", "cruel"]

    // const miFuncion = ()=>{}
    const message = computed(function () {
        let message;
        if (checked.value) {
            message = 'Apagar'
        } else {
            message = 'Encender'
        }
        return message
        // return checked.value ? 'Apagar' : 'Encender'
    })
</script>


<template>
    <ul>
        <li v-for="(text, index) in items" :key="index">
            {{ text }} - {{ index }}
        </li>
    </ul>

    <div class="bg-blue-400 inline-block text-white rounded  py-1 px-2 " :class='{"bg-orange-400" : checked, "text-black":checked}'
    >
        Hola este es un mensaje
    </div>

    <input type="checkbox" id="checkbox" v-model="checked">

    <!-- Opc 1 -->
    <!-- Aplicando operador ternario que es como el if y else -->
    <!-- <label for="checkbox">{{ checked ? 'Apagar' : 'Encender' }}</label> -->
    
    <!-- Opc 2 -->
    <label for="checkbox">{{ message }}</label>

    <div>
        <input class="border-gray-300 border-2" v-model="text">
    </div>
    {{ text }}

</template>