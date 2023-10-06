<template>
    <h1 @click="changeMessage">
        {{ msg }}
    </h1>
    <h1>{{ reversedMessage }}</h1>
</template>

<script>

export default {
    data() {
        return {
            msg: 'Hello?'
        }
    },
    computed: {
        reversedMessage() {
            return this.msg.split('').reverse().join('')
        }
    },
    watch: {
        // 데이터의 변화를 감시하는 용도, computed 데이터도 감시 가능
        // 변화된 데이터를 인자로 받아서 사용할 수 있음
        msg(newValue) {
            console.log('msg:', newValue)
        },
        reversedMessage(newValue) {
            console.log('reversedMessage:', newValue)
        }

    },
    methods: {
        changeMessage() {
            this.msg = 'Good!'
        }
    }
}
</script>

<style>
h1 {
    margin: 0;
}
</style>
