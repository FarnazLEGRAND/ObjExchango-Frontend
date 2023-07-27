<script lang="ts" setup>
import { Objet } from 'entities';
//data . reflesh  pour relance,... il fait requet ver backend avec use fetch
const { data, refresh } = useFetch<Objet[]>('http://localhost:8000/api/objet');


</script>

<template>
  <div class="container">

    <!-- <Form @submitObjet="addOPbjet($event)"/> -->

    <!-- <p v-for="item of data">{{ item.title }}</p> -->
    <!-- component adress -->
    <ObjetItem v-for="item of data" :objet="item" />
  </div>
</template>

<style scoped></style>