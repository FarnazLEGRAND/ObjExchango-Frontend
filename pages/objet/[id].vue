<script lang="ts" setup>
import { Objet } from "../../entities";

const route = useRout();

const { data } = useFetch<Objet>('http://localhost:8000/api/objet/id/' + route.params.id);

</script>

<template>
  <div v-if="data">
    <h3>{{ data.title }}</h3>
    <p>Description : {{ data.description }}</p>
    <p>Comment : {{ data.category }}</p>
  </div>
</template>