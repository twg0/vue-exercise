<template>
    <button @click="handler">
        Click me!
    </button>
<!--  template 로 묶으면 개발자 도구에서 감싸져 있다는 것이 표현되지 않음, div 의 경우 묶음이 표현됨  -->
<!--  최상위 template 태그에는 v-if를 사용하지 말 것  -->
<!--    <template v-if="isShow">-->
<!--        <h1>Title</h1>-->
<!--        <p>Paragraph 1</p>-->
<!--        <p>Paragraph 2</p>-->
<!--    </template>-->
<!--  v-if 는 true가 아니라면 요소 자체를 만들지 않음  -->
    <h1 v-if="isShow">
        Hello?!
    </h1>
<!--  v-show 는 true와 false에 상관 없이 렌더링은 함, 개발자도구에 표기됨  -->
<!--  v-show 는 template 에서 지원되지 않고 v-else 사용 불가  -->
    <h1 v-show="isShow">
        Hello?!
    </h1>
<!--  v-show 와 v-if 의 차이는 렌더링의 비용, v-if 는 lazy 하기 때문에 전환 비용이 높음, v-show 는 초기 렌더링 비용이 높다  -->
<!--  전환되는 빈도에 따라 골라서 사용하는 것이 좋다  -->
</template>

<script>

export default {
    data() {
        return {
            isShow: false,
            count: 0
        }
    },
    methods: {
        handler() {
            this.isShow = !this.isShow
            this.count++;
        }
    }
}
</script>

<style>
h1 {
    margin: 0;
}
</style>
