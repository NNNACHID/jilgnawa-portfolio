<script setup lang="ts">
import { onMounted } from 'Vue';
import AOS from 'aos'
import 'aos/dist/aos.css'

onMounted(()=>{
    AOS.init();
})
</script>
<template>
    <div>
        <h1 class="text-3xl font-bold underline">
            Hello world!
        </h1>
    </div>
</template>

<style>
</style>
