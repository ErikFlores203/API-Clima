<script setup>
import useclima from '../composables/useClima';
    const {formatearTemp} = useclima()

    defineProps({
        clima:{
            type:Object,
            required:true
        }
    })
</script>

<template>
    <div class="resultado">
        <h2>Clima de:{{ clima.name }}</h2>
        <p class="actual">&deg;C{{ formatearTemp(clima.main.temp) }}</p>
        <div class="temperaturas">
            <p>Min: {{ formatearTemp(clima.main.temp_min) }}<span>&deg;C</span></p>
            <p>Max: {{ formatearTemp(clima.main.temp_max) }}<span>&deg;C</span></p>
        </div>
    </div>
</template>
