<script lang="ts" setup>
import { Borrow} from 'entities';
//data . reflesh  pour relance,... il fait requet ver backend avec use fetch
const { data, refresh } = useFetch<Borrow[]>('http://localhost:8000/api/borrow');

async function addObjet(borrow: Borrow) {
  await $fetch('http://localhost:8000/api/borrow', {
    method: 'POST',
    body: borrow
  });
  refresh();
}
</script>

<template>
  <div class="container">

    <!-- <Form @submitObjet="addOPbjet($event)"/> -->

    <!-- <p v-for="item of data">{{ item.objet.title}}</p> -->
    <!-- component adress -->
    <BorrowList v-for="item of data" :borrow="item" />
  </div>
</template>

<style scoped></style>