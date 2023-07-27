<script lang="ts" setup>
import { Objet } from 'entities';

const {data, refresh} = useFetch<Objet[]>('http://localhost:8000/api/objet');

async function addObjet(objet:Objet) {
    await $fetch('http://localhost:8000/api/dog', {
        method: 'POST',
        body: objet
    });
    refresh();
}
</script>    
<template>
 
    <FormeObjet @submitDog="addObjet($event)" />
 
</template>

<style scoped></style>
