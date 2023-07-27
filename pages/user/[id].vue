
<script lang="ts" setup>
import { User } from "../../entities";

const route = useRoute();

const { data } = useFetch<User>('http://localhost:8000/api/user/id/' + route.params.id);

</script>

<template>
  <div v-if="data">
    <h3>{{ data.name }}</h3>
    <p>email : {{ data.email }}</p>
    <p>password : {{ data.password }}</p>
  </div>
</template>




