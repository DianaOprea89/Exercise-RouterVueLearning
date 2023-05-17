<script setup>
import {useRoute, useRouter, RouterView} from "vue-router"
import cars from "../data/cars.json"


const route = useRoute();
const router = useRouter();
let carId= parseInt(route.params.id.toString());
const car = cars.find(c => c.id === carId);
const showContact = () => {
  if (carId === 4) return;
  return router.push(`/cars/${carId}/contact`);
}

const {price, name, year} = car; // Destructure properties
</script>
<template>
  <div v-if="car">
    <h1>Car View</h1>
    <p>{{ name }}</p>
    <p>{{ year }}</p>
    <p>{{ price }}</p>
    <button @click="showContact">Click for contact</button>
    <RouterView/>
  </div>
  <div v-else>
    <h1>Car not found</h1>
  </div>
</template>

