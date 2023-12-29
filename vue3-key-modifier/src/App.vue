<template>
<!--  .enter 엔터가 눌렸을 때만 handler 동작  -->
<!--  .원하는 키 를 입력하면 handler 동작  -->
<!--  체이닝으로 작성하면 전부 눌려있어야 동작  -->
    <input type="text"
    @keydown.ctrl.a="handler">
</template>

<script>

export default {
    methods: {
        handler() {
            console.log('Enter!!')
/*            if (event.key === 'Enter') {
                console.log('Enter!!');
            }*/
        }
    }
}
</script>

