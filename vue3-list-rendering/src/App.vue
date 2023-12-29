<template>
    <button @click="handler">
        Click me!
    </button>
    <ul>
        <!--  객체 구조 분해  -->
<!-- :key 키를 데이터와 연결할 때 사용 -->
<!-- v-for의 첫번째요소는 데이터에 해당하는 요소, 두번째는 수치적으로 몇번째인지 인지하는 변수 -->
<!--    newFruits 를 통해 id와 name 으로 이루어진 새로운 구조체가 적용됨    -->
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
