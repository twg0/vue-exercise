<template>
    <!--  large 하나만 쓰는 이유 : 객체 데이터 내부에서 속성과 데이터가 동일하면 하나로 축약 가능, 원래는 {large:large}  -->
    <div
        :class="{large}"
        :style="{backgroundColor: color}"
        class="btn">
        <!--    {{text}} 를 통해 props로 받은 텍스트를 입력할 수 있다.    -->
        <!--    content로 입력한 모든 요소를 slot으로 받아서 출력되는 위치를 지정할 때 slot을 사용한다. span이 적용됨    -->
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: "MyBtn",
    props: { // 부모와 자식간의 데이터 통신 방법
        color: {
            type: String,
            default: 'gray'
        },
        large: {
            type: Boolean,
            default: false
        },
        text: {
            type: String,
            default: ''
        }
    }
}
</script>

<style scoped lang="scss">
.btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;

    &.large { // scss 문법 : .btn.large
        font-size: 20px;
        padding: 10px 20px;
    }
}
</style>