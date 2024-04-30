<script setup>
    const character = defineProps(["name", "species", "url", "episode", "gender", "location", "image", "status"])
    import { ref } from "vue";
</script>

<template>

    <div class="card mb-3 ms-5 card-personagens efeito-vidro">
        <div class="row g-0">
            <div class="col-md-4">
                <img :src=character.image class="img-fluid mt-3">
            </div>
            <div class="col-md-8">
                <div class="card-body">
                    <h5 class="card-title">{{ character.name }}</h5>
                    <span class="text-danger">Status: </span>
                    <span v-if="character.status === 'Alive'" class="text-primary">{{ character.status }}</span>
                    <span v-else-if="character.status === 'Dead'" class="text-danger">{{ character.status }}</span>
                    <span v-else-if="character.status === 'unknown'" class="text-warning">{{ character.status }}</span>
                    <span v-else class="text-bg-danger">{{ character.status }}</span>
                    
                    <h6 class="card-text"><b class="text-danger">Espécie:</b> {{ character.species }} </h6>
                    <h6 class="card-text"><b class="text-danger">Gênero:</b> {{ character.gender }}</h6>
                    <p class="card-text"><b class="text-danger">Localização Atual:</b> {{ character.location }}</p>
                    <span class="text-success"><b class="text-danger">Total de episódios:</b> {{ character.episode.length }}</span>

                </div>
            </div>
        </div>
    </div>

</template>

<style>

</style>