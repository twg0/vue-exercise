<template>
    <li>{{ name }}?!</li>
</template>

<script>
export default {
    props: {
        name: {
            type: String,
            default: ''
        }
    }
}
</script>

<style scoped>
h1 {
    color: red !important;
}
</style>