<script lang="ts" setup>
import { Objet } from 'entities';

// Get current route instance
const route = useRoute()

const { data, refresh } = useFetch<Objet>(async () => {
    console.log(route.params)
    const objectId = route.params.id

    const response = await fetch(`http://localhost:8000/api/objet/${objectId}`)

    const data = await response.json()

    return data
});
console.log(data.value)
</script>    
<template>
    <ObjetItem objet=data />
</template>

<style scoped></style>
