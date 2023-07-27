<script lang="ts" setup>
import { Borrow} from "../entities";
defineProps<{
  borrow: Borrow
}>()

</script>

<template>
  <div>
    <h3>
      <NuxtLink :to="'/borrow/' + borrow._id">{{ borrow.objet.title }}</NuxtLink>
    </h3>
    <p>{{borrow.requestDate }}</p>
    <p>{{borrow.borrowDate}}</p>
    <p>{{borrow.returnDate}}</p>
    <p>{{ borrow.objet.description }}</p>
    <p>{{borrow.objet.category }}</p>
  </div>
</template>

<style scoped></style>

