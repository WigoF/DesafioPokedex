<script setup>

const pokemon = defineProps(['name','baseUrlSvg'])


</script>

<template>
    <div class="col-4">
        <div class="card p-4 mb-3">
            
            <img 
            :src="baseUrlSvg"
            height="90"
            />
            
            <strong class="text-center">{{ name }}</strong>

        </div>
    </div>
</template>

<style scoped>


</style>