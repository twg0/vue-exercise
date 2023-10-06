<template>
    <button @click="add">
        ADD
    </button>
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
    data() {
        return {
            // Getter, Setter
            msg: 'Hello Computed!'
        }
    },
    computed: {
        // computed 에서 이미 계산된 요소는 재사용될 때 캐싱되어 사용됨
        // 기본적으로 값을 얻어내는 방식으로만 사용됨 = Getter
        // reversedMessage() {
        //     return this.msg.split('').reverse().join('')
        // }
        // 예외로 Setter 를 지정해줄 수 있음
        reversedMessage: {
            get() {
                return this.msg.split('').reverse().join('')
            },
            set(newValue) {
                // this.msg = newValue
                console.log(newValue)
            }
        }
    },
    methods: {
        add() {
            // 여기서 newValue로 !?가 붙은 값이 들어감
            this.reversedMessage += '!?'
        }
    }
}
</script>

<style>
h1,h2,h2,h3,h4,h5,h6 {
    margin: 0;
}
button {
    margin: 0;
}
</style>
