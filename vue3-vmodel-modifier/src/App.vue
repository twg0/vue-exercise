<template>
    <!--  @input은 넣으면 바로바로 바뀐다.  -->
    <!--  @change는 입력 중에는 바뀌지 않고 완료(엔터, 다른곳 클릭 등) 하면 바뀐다.  -->
    <!--  .lazy 는 @change와 동일하게 동작한다.  -->
    <h1>{{ msg }}</h1>
    <input
        type="text"
        v-model.lazy="msg">
    <!--  입력되는 데이터의 타입을 유지시킬 수 있다.  -->
    <input
        type="text"
        v-model.number="msg">
    <!--  .trim 은 trim()과 동일한 동작을 한다.  -->
    <!--  이때 watch가 동작하지 않는데, v-model에서 trim이 미리 적용되어서 앞 뒤에 공백을 넣더라도 지워지고 data의 msg와 동일하다고 판단하여 watch가 동작하지 않는다.  -->
    <input
        type="text"
        v-model.trim="msg">
</template>

<script>

export default {
    data() {
        return {
            msg: 'Hello world!',
        }
    },
    watch: {
        msg() {
            // console.log(typeof this.msg)
            // console.log(this.msg.trim())
            console.log(this.msg)
        }
    }
}
</script>

