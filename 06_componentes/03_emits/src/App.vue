<script setup>
import { reactive } from 'vue'

import MostrarTareas from "@/components/MostrarTareas.vue";
import AgregarTareas from '@/components/AgregarTareas.vue'

const listaTareas = reactive([
    {
        id: 1,
        texto: 'Ir al supermercado'
    },
    {
        id: 2,
        texto: 'Bañar al perro'
    }
])

const agregarTarea = (nuevaTarea) => {
    listaTareas.push({
        id: listaTareas.length + 1,
        texto: nuevaTarea
    })
}
</script>

<template>
    <h1>Ejemplo emits</h1>
    <hr class="mb-5">

    <MostrarTareas :tareas="listaTareas" titulo="Tareas actuales"/>
    <AgregarTareas @agregar="agregarTarea"/>
</template>

<style scoped>
</style>
