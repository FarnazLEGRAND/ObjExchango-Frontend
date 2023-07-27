<script lang="ts" setup>
import {Objet} from 'entities';

async function addObjet(objet:Objet) {
    await $fetch('http://localhost:8000/api/objet', {
        method: 'POST',
        body: objet
    });
}
    
</script>


<template>
    <FormeObjet @submitDog="addObjet($event)" />

</template>

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
}
</style>