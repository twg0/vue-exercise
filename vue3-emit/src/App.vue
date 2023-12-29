<template>
<!--  이벤트는 요소에 명확히 연결되었을 때 동작함, 이것도 최상위에 속성이 상속되는 것이다  -->
    <MyBtn @heropy="log" @change-msg="logMsg">
        Banana
    </MyBtn>
</template>

<script>

import MyBtn from "@/components/MyBtn.vue";

export default {
    components: {MyBtn},
    methods: {
        log(event) {
            console.log('Click!!')
            console.log(event)
        },
        logMsg(msg) {
            console.log(msg)
        }
    }
}
</script>
