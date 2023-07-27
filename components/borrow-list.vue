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
    <div class="card mb-4" style="width: 18rem">
    <div class="card-body">
    <h3 class="card-title">
      <NuxtLink :to="'/borrow/' + borrow._id">{{ borrow.objet.title }}</NuxtLink>
    </h3>
    <p class="card-text">{{ formatDate(borrow.requestDate) }}</p>
    <p class="card-text">{{ formatDate(borrow.borrowDate) }}</p>
    <p class="card-text">{{ formatDate(borrow.returnDate) }}</p>
    <p class="card-text">{{ borrow.objet.description }}</p>
    <p class="card-text">{{borrow.objet.category }}</p>
    <p class="card-text">{{borrow.objet.owner}}</p>
</div>
</div>
    <p>{{borrow.borrower.name}}</p>
  </div>
</template>

<style scoped></style>

