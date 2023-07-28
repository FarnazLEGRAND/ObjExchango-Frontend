<script lang="ts" setup>
import { Borrow } from "../../entities";

const route = useRoute();

const { data } = useFetch<Borrow>(
  "http://localhost:8000/api/borrow/" + route.params.id
);

async function handleBorrow() {
  // 1. je cree le borrow correspondant a cet objet. 
  // pour ceci je vais faire un appel a l api
  const response = await $fetch("http://localhost:8000/api/borrow/", {
    // 2. une fois le borrow cree je redirige dessus en utilisant navigateTo. 
    // Son url sera /api/borrow/id
    "method": "POST",
    "body": {
    "borrower":{
        "name":"saba",
        "email":"saba@me.com",

    },
    "objet":data.value}
  });

  await navigateTo('/borrow/' + response._id)
  // passing 'to' as a string
};
</script>

<template>
  <div class="container">
    <div v-if="data">
      <h3>{{ data.borrower._id }}</h3>
      <p>Accepted : {{ data.borrowDate }}</p>
      <p>Rendu : {{ data.returnDate }}</p>
      <p>Duration : {{ data.requestDate }}</p>
      <p>borrower:{{ data.borrower.name }}</p>
    </div>
 
    <form @submit.prevent="handleBorrow()" enctype="multipart/form-data" class="col-6 mt-4" style="margin: auto"> 
      <button class="btn btn-primary"  style="background-color: #8cd2d0;">Accept it</button>
     <button class="btn btn-primary"  style="background-color: #f17094;">Return</button>    
    </form>
  </div>
</template>

<!-- Rajouter un bouton accepter la requete de location: handle + formulaire -->
<!-- Rajouter un bouton restituer l'objet: handle + formulaire -->

<style>

</style>