<script setup lang="ts">
import { ref, onMounted } from "vue"
import autoAnimate from "@formkit/auto-animate"

let numbers = ref(Array.from({ length: 100 }, (y, i) => i))
function shuffle() {
    numbers.value.sort(() => 0.5 - Math.random())
}
let container = ref();
onMounted(() => {
    autoAnimate(container.value);
})
</script>

<template >
    <section ref="container" class="flex flex-wrap gap-4">
        <div v-for="number in numbers" :key="number" v-text="number" class="bg-gray-200 w-12 h-12 flex items-center justify-center">
        </div>
    </section>
    <div class="fixed bottom-4 right-4">
        <!-- <button class="bg-black rounded text-white" @click="numbers.unshift(100)">
            Add
        </button>
        <button class="bg-black rounded text-white" @click="numbers.push(100)">
            Add
        </button> -->
        <button class="bg-black rounded text-white" @click="shuffle">
            Shuffle
        </button>
    </div>
</template>

<style scoped>

</style>