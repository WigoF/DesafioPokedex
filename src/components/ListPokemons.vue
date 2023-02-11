<script setup>

const pokemon = defineProps(['name','baseUrlSvg'])


</script>

<template>
    <div class="col-12 col-sm-6 col-md-4 col-lg-3-">
            <div class="card p-4 mb-3 cardListPokemon">
                
                <img 
                :src="baseUrlSvg"
                height="80"
                />
                
                <strong class="text-center">{{ name }}</strong>

            </div>
    </div>
</template>

<style scoped>
.cardListPokemon{
    background: rgb(4,12,164);
    background: linear-gradient(211deg, rgba(4,12,164,1) 0%, rgba(91,179,239,0.958420868347339) 58%);

    cursor: pointer;
}
.cardListPokemon:hover{
    background: rgb(72,63,251);
    background: radial-gradient(circle, rgba(4,12,164,1) 0%, rgba(91,179,239,0.6) 100%);
}
.cardListPokemon img:hover{
    padding: .1rem;
}

</style>