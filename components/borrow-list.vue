<script lang="ts" setup>
import { Borrow } from "../entities";
defineProps<{
  borrow: Borrow
}>()

// create a method for date conversion
const formatDate = (date: Date | null) => {
  if (date) {
      return new Date(date).toLocaleString('en-US');
  } else {
    return '-';
  }
};
</script>

<template>
  <div>
    <h3>
      <NuxtLink :to="'/borrow/' + borrow._id">{{ borrow.objet.title }}</NuxtLink>
    </h3>
    <p>{{ formatDate(borrow.requestDate) }}</p>
    <p>{{ formatDate(borrow.borrowDate) }}</p>
    <p>{{ formatDate(borrow.returnDate) }}</p>
    <p>{{ borrow.objet.description }}</p>
    <p>{{borrow.objet.category }}</p>
    <p>{{borrow.objet.owner}}</p>
  </div>
</template>

<style scoped></style>

