<template>
    <div
        class="btn">
        <slot></slot>
    </div>
    <!--  emits에 상위의 click이 전달되고, emit()을 통해 사용이 된다.  -->
    <!--  상위의 요소가 반드시 click이라는 요소가 아니어도 된다. 이곳에서 click을 하면 emit을 통해 상위의 log 메소드가 동작한다.  -->
    <!--  dblclick : 더블클릭  -->
    <!--  두번째 요소로 변수를 줄 수 있음 -->
    <h1 @dblclick="$emit('heropy', $event)">ABC</h1>
    <input type="text" v-model="msg"/>
</template>

<script>
export default {
    emits: [
        'heropy',
        'changeMsg'
    ],
    data() {
        return {
            msg: ''
        }
    },
    watch: {
        msg() {
            this.$emit('changeMsg', this.msg)
        }
    }
}
</script>

<style scoped>
.btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
}
</style>