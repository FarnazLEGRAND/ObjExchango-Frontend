<script lang="ts" setup>
import { Objet } from "../entities";
//const emit = defineEmits(['submitObjet'])
const emit = defineEmits<{
  (e: 'submitObjet', objet: Objet): void
}>();

const objet = ref<Objet>({
  title: '',
  description: '',
  category: ''
  owner:
        ({_id:'',
         } )

});

function handleSubmit() {
  emit('submitObjet', objet.value)
}

</script>

<template>
  <form @submit.prevent="handleSubmit()" enctype="multipart/form-data" class="col-6 mt-4" style="margin: auto"></form>

  <div class="group log-input">
    <label for="title">Title : </label>
    <input id="title" type="text" name="title" v-model="objet.title">
  </div>
  <!-- <div class="group log-input">
    <label for="pic">pic. : </label>
    <input id="pic" type="file" name="pic">
  </div> -->
  <div class="group log-input">
    <label for="description">Description : </label>
    <input id="description" type="text" name="description" v-model="objet.description">
  </div>
  <div class="group log-input">
    <label for="category">Category : </label>
    <input id="category" type="text" name="category" v-model="objet.category">
  </div>
  <div class="group log-input">
    <label for="owner">Owner: </label>
    <input id="owner" type="text" name="owner" v-model="objet.owner">
  </div>
  <button>Submit</button>
</form></template>

<style scoped></style>