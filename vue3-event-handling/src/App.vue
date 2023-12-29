<template>
    <button @click="handler('hi', $event)">
        Click 1
    </button>
    <button @click="handler('what', $event)">
        Click 2
    </button>
    <button @click="handlerA(), handlerB()">
        Click me!
    </button>
</template>

<script>

export default {
    methods: {
        // 첫번째로 들어오는 변수는 event 에 대한 정보를 가지고 있음
        // handler(event) {
        //     // event 객체 사용 가능
        //     console.log(event)
        //     console.log(event.target.textContent)
        //     console.log(event.target)
        // }
        // 따로 인수를 넣으면 넣은 인수를 다루게 되고, 넣지 않으면 event 객체를 사용하게 된다.
        handler(msg, event) {
            // event 객체 사용 가능
            console.log(msg)
            console.log(event)
        },
        // 여러개의 메소드를 한 번에 호출할 수도 있음
        handlerA() {
            console.log('A')
        },
        handlerB() {
            console.log('B')
        }
    }
}
</script>

<style>

</style>
