<script setup>

import {onMounted, reactive, ref} from "vue";
import PersonagensSerie from "../components/listaPersonagens.vue";

let personagens = reactive(ref())

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results

  })
})

</script>

<template>
  <main>
    <div class="container-fluid">
      <div class="col-lg-12 mt-4">

          <div class="card-body row">
              <PersonagensSerie
              v-for="p in personagens"
              :key="p.name"
              :url="p.url"
              :status="p.status"
              :location="p.location.name"
              :gender="p.gender"
              :name="p.name"
              :episode="p.episode"
              :image="p.image"
              :species="p.species"
            />
          </div>
          
      </div>
    </div>
  </main>
</template>
