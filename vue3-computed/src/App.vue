<template>
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
    data() {
        return {
            msg: 'Hello Computed!'
        }
    },
    computed: {
        // computed 에서 이미 계산된 요소는 재사용될 때 캐싱되어 사용됨
        reversedMessage() {
            return this.msg.split('').reverse().join('')
        }
    },
    // methods: {
    //     reverseMessage() {
    //         return this.msg.split('').reverse().join('')
    //     }
    // }
}
</script>

<style>
h1,h2,h2,h3,h4,h5,h6 {
    margin: 0;
}
</style>
