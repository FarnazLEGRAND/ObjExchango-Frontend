<script lang="ts" setup>
import { User} from "../../entities";

const route = userRout();

const { data } = userFetch<User>('http://localhost:8000/api/user/id/' + route.params.id);

</script>

<template>
  <div v-if="data">
    <h3>{{ data.title }}</h3>
    <p>Description : {{ data.description }}</p>
    <p>Comment : {{ data.category }}</p>
  </div>
</template>