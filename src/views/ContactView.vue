<script setup>
import {useRoute} from "vue-router";
import cars from "../data/cars.json"
const route=useRoute()
 const car= cars.find(c =>  c.id === parseInt(route.params.id.toString()))
const { contact, dealer, number } = car; // Destructure properties
</script><template>
<div  v-if="car">
  <h1> Contact Info</h1>
  <p>{{contact.dealer}}</p>
  <p>{{contact.number}}</p>
</div>
</template>

