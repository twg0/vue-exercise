<template>
<!--  기본적인 컨텐트를 삽입하면 전부 대체 되는데, 만약 없다면 slot 태그 안에 있는 요소들이 대체된다. slot 사이에 있는 컨텐츠를 fallback(대체) 컨텐츠라고 한다  -->
    <div
        class="btn">
        <slot name="icon"></slot>
        <slot name="text"></slot>
    </div>
</template>

<script>
export default {
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