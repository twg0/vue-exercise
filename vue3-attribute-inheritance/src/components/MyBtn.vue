<template>
    <!--  상위의 class에 입력한 heropy가 아래 btn heropy 형태로 나타나게 되는데 이것이 상속  -->
    <!--  상위에서 입력한 heropy가 형제 div를 생성하는 순간 class 에서 사라지게됨, 최상위 요소가 두개  -->
    <!--  최상위 요소에 들어가게 되는데 어떤 요소로 들어갈지 지정하지 않는다면 적용이 안됨  -->
    <div class="btn">
        <slot></slot>
    </div>
    <!--  class 혹은 style 중 원하는 것을 골라서 사용하는 방법  -->
    <h1 :class="$attrs.class"
        :style="$attrs.style"></h1>
    <!--  모두 적용하는 방법  -->
    <h1
        v-bind="$attrs"></h1>

</template>

<script>
export default {
    name: "MyBtn",
    inheritAttrs: false, // 속성의 상속을 지정해주는 부분, false로 하면 최상위가 하나만 있더라도 상속이 발생하지 않는다.
    created() { // 생성된 직후에 동작
        console.log(this.$attrs)
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