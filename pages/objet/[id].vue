<script lang="ts" setup>
import {Objet } from "../../entities";

const route = useRoute();

const { data, refresh } = useFetch<Objet>(
  "http://localhost:8000/api/objet/" + route.params.id
);
async function updateObjet(objet:Objet) {
  await $fetch("http://localhost:8000/api/objet/" + route.params.id, {
    method: "PATCH",
    body:objet,
  });
  refresh();
}
function removeObjet() {
  $fetch("http://localhost:8000/api/objet/" + route.params.id, {
    method: "DELETE",
  });
  refresh();
}

const emit = defineEmits(["submit"]);

function handleSubmite() {
  emit("submit",objet.value);
}


const objet = ref<Objet>({
  title: '',
  description: '',
  category: '',
  owner: {
    _id: '',
    name: '',
  }
});
</script>

<template>
  <div v-if="data">
    
    <h3>{{ data.title }}</h3>
    <p>Description : {{ data.description }}</p>
    <p>Comment : {{ data.category }}</p>
    <p>Owner:{{ data.owner.name}}</p>
  </div>
</template>


