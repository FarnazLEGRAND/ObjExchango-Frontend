<script lang="ts" setup>
import { Objet, User } from "../entities";
//const emit = defineEmits(['submitObjet'])
const emit = defineEmits<{
  (e: 'submitObjet', objet: Objet): void
}>();

const objet = ref<Objet>({
  title: '',
  description: '',
  category: '',
  owner: {
    _id: '',
    name: '',
  }
});

function handleSubmit() {
  emit('submitObjet', objet.value)
}

</script>

<template>
  <form @submit.prevent="handleSubmit()" enctype="multipart/form-data" class="col-6 mt-4" style="margin: auto">

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
    <textarea id="description" type="text" name="description" v-model="objet.description"></textarea>
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

<style >
input[type="text"], input[type="email"], input[type="password"], textarea, select {
    background: transparent;
    border: none;
    font-family: "Montserrat";
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 0.2em;
    line-height: 24px;
    height: 42px;
    padding-left: 20px;
    padding-right: 20px;
    text-transform: none;
    width: 100%;
}

input[type="checkbox"]:not(:checked) + label, input[type="checkbox"]:checked + label {
    color: #aaaaaa;
    cursor: pointer;
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 0.3em;
    padding-left: 10px;
    padding-top: 6px;
    position: relative;
    text-transform: uppercase;
}</style>