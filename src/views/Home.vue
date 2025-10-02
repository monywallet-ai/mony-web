<script setup lang="ts">
import { useCounterStore } from '@/store/counter'
import { computed } from 'vue';

const counterStore = useCounterStore()

const isZero = computed(() => {
    return counterStore.count === 0
})


</script>

<template>
    <div>
        <h1>Simple counter</h1>
        <p>Count is: {{ counterStore.count }}</p>
        <button @click="counterStore.increment">Increment</button>
        <button v-if="!isZero" @click="counterStore.decrement">
            Decrement
        </button>
    </div>
</template>

<style scoped>
div {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;

    &>button {
        margin-top: 20px;
    }
}

h1 {
    font-weight: 500;
    font-size: 2.6rem;
    top: -10px;
}

p {
    font-size: 1.5rem;
}

button {
    font-size: 1.25rem;
    font-weight: 500;
    background-color: #4caf50;
    color: white;
    padding: 10px 20px;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease;

    &:hover {
        background-color: #3e8e41;
    }
}
</style>