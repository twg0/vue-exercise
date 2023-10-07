<template>
    <button @click="handler">
        Click me!
    </button>
    <ul>
        <!--  객체 구조 분해  -->
        <li
            v-for="{id, name} in newFruits"
            :key="id">
            {{ name }}-{{ id }}
        </li>
    </ul>
</template>

<script>
import shortid from 'shortid'

export default {
    data() {
        return {
            fruits: ['Apple', 'Banana', 'Cherry']
        }
    },
    computed: {
        newFruits() {
            return this.fruits.map(fruit => ({
                id: shortid.generate(),
                name: fruit
            }))
        }
    },
    methods: {
        handler() {
            this.fruits.push('Orange')
        }
    }
}
</script>

<style>
ul {
    list-style-type: none;
    padding: 0;
}
</style>
