<script setup lang="ts">
import { onMounted } from 'vue';
import Header from './components/Header.vue';
import AOS from 'aos'
import 'aos/dist/aos.css'

onMounted(()=>{
    AOS.init();
})
</script>

<template>
    <div>
        <Header />
    </div>
</template>

<style>
</style>
