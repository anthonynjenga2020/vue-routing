<script setup>
import {useRoute} from 'vue-router'
import {onBeforeMount, ref} from "vue"
import cars from "../data.json"

const car = ref(null)
const route = useRoute()
const {id} = route.params

onBeforeMount(() => {
    car.value = cars.find(c => c.id === parseInt(id))
})


</script>

<template>
    <div class="container">
        <div v-if="car">
            <h1>The Car</h1>
             <p>Make: {{ car.make }}</p>
             <p>Body: {{ car.body }}</p>
             <p>Price: {{ car.price }}</p>
             <p>year: {{ car.year }}</p>
        </div>
    
    <div v-else> 
    <h1>Car not found</h1>
    </div>  
    </div>
</template>