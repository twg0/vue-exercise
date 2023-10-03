<template>
    <h1 @click="increase">{{ count }}</h1>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <div v-if="count > 4">
        4보다 큽니다!
    </div>
    <ul>
        <FruitNames v-for="fruit in fruits" :key="fruit" :name="fruit">
            {{ fruit }}
        </FruitNames>
    </ul>
</template>

<script>
import FruitNames from './components/FruitNames.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
    name: 'App',
    components: {
        HelloWorld,
        FruitNames
    },
    data() {
        return {
            count: 0,
            fruits: ['Apple', 'Banana', 'Cherry']
        }
    },
    methods: {
        increase() {
            this.count += 1
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

h1 {
    font-size: 50px;
    color: royalblue;
}

li {
    list-style: none;
}
</style>
