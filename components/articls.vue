<script lang="ts" setup>
import { Objet } from "../entities";
defineProps<{
  objet: Objet
}>()

</script>

<template>
  <div class="container-fluid" style="width:100vw">
    <div class="container text-center">
      <div class="row" style="margin: 20px; width:30% ">
        <div class="card-body">
      <h3 class="card-title">
        <NuxtLink :to="'/objet/' + objet._id">{{ objet.title }}</NuxtLink>
      </h3>
      <p class="card-text">{{ objet.description }}</p>
      <p class="card-text">{{ objet.category }}</p>
    </div>
    </div>
  </div>
  </div></template>

<style scoped></style>