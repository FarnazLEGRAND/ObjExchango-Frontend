<script lang="ts" setup>
import { Borrow  } from "../../entities";

const route = useRoute();

const { data } = useFetch<Borrow >(
  "http://localhost:8000/api/borrow/" + route.params.id
);
</script>

<template>
  <div v-if="data">
    <h3>{{ data.borrower._id }}</h3>
    <p>Accepted : {{ data.borrowDate }}</p>
    <p>Rendu : {{ data.returnDate }}</p>
    <p>Duration : {{ data. requestDate }}</p>
    <p>borrower:{{ data.borrower.name }}</p>
  </div>
</template>

<!-- Rajouter un bouton accepter la requete de location: handle + formulaire -->
<!-- Rajouter un bouton restituer l'objet: handle + formulaire -->