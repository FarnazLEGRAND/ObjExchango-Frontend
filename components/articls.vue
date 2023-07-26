<script lang="ts" setup>
import { Objet } from "../entities";
defineProps<{
  objet: Objet
}>()

</script>

<template>
  <div>
    <h3>
      <NuxtLink :to="'/objet/' + objet._id">{{ objet.title }}</NuxtLink>
    </h3>
    <p>{{ objet.description }}</p>
    <p>{{ objet.category }}</p>
  </div>
</template>

<style scoped></style>