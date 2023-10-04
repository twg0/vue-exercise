<template>
<!--
active 를 '' 으로 감싸는 이유 : 현재 v-bind의 약어로 쓰였기 때문에 단순한 active 는 인식하지 못한다. html과 별개
msg 를 직접 사용하지 않은 이유 : 클릭시 data의 msg 가 직접 변하기 때문에 h1의 class 가 클릭마다 계속 변하게 되어 style 이 적용되지 않게 된다.-->
    <h1 :[attr]="'active'" @[event]="add">
        {{ msg }}
    </h1>
</template>

<script>
export default{
    data() {
        return {
            msg: 'active',
            attr: 'class',
            event: 'click'
        }
    },
    methods: {
        add() {
            this.msg += '!'
        }
    }
}
</script>

<style scoped>
.active {
    color: royalblue;
    font-size: 100px;
}
</style>
