<script lang="ts" setup>
import { Objet } from "../../entities";

const route = useRoute();

const { data, refresh } = useFetch<Objet>(
  "http://localhost:8000/api/objet/" + route.params.id
);

async function updateObjet(objet: Objet) {
  await $fetch("http://localhost:8000/api/objet/" + route.params.id, {
    method: "PATCH",
    body: objet,
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
  emit("submit", objet.value);
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

// https://fr.wikipedia.org/wiki/Post-redirect-get
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
  <div class="container" v-if="data">
    <div class="card mb-4" style="width: 18rem">
      <div class="card-body">
        <h3 class="card-text">{{ data.title }}</h3>
        <p class="card-text">Description : {{ data.description }}</p>
        <p class="card-text">Comment : {{ data.category }}</p>
      </div>
    </div>
    <p>Owner:{{ data.owner.name }}</p>
    <form @submit.prevent="handleBorrow()" enctype="multipart/form-data" class="col-6 mt-4" style="margin: auto">
      <button class="btn btn-primary">Borrow it</button>
    </form>
  </div>
</template>


