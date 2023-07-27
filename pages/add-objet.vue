<script lang="ts" setup>
import { Objet } from "../entities";

const { refresh } = useFetch<Objet[]>("http://localhost:8000/api/objet");

async function postObjet(){
  await $fetch('http://localhost:8000/api/objet', {
    method: 'POST',
    body: Object.values
  })
  refresh();
}



</script>


 
  <FormeObjet @submitDog="addObjet($event)" />

</template>