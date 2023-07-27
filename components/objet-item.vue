<script lang="ts" setup>
import { Objet } from "../entities";
defineProps<{
  objet: Objet
}>()

</script>

<template>
  <div>
    <div class="card mb-4" style="width: 18rem">
    <div class="card-body">
    <h3 class="card-title">
      <NuxtLink :to="'/objet/' + objet._id">{{ objet.title }}</NuxtLink>
    </h3>
    <p class="card-text">{{ objet.description }}</p>
    <p class="card-text">{{ objet.category }}</p>
    <!-- <p>Owner:{{ objet.owner.name}}</p> -->
  </div>
  </div>
  </div>
</template>

