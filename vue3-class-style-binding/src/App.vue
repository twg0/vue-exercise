<template>
<!--  클래스  -->
<!--  isActive 가 초기에는 false 이기 때문에 class 가 연결되지 않지만 true 로 변경되면 진실성에 의해 결정이됨  -->
<!--  배열도 사용 가능, 유용한지는 모름  -->
    <h1
        :class="{ active: isActive }"
        @click="activate">
        Hello?!({{ isActive }})
    </h1>
<!--  스타일 바인딩  -->
    <h1 :style="[fontStyle,backgroundStyle]"
    @click="changeStyle">
        Hello?!
    </h1>
</template>

<script>

export default {
    data() {
        return {
            isActive: false,
            fontStyle: {
                color: 'orange',
                fontSize: '30px'
            },
            backgroundStyle: {
                backgroundColor: 'black'
            }
        }
    },
    methods: {
        activate() {
            this.isActive = true
        },
        changeStyle() {
            this.fontStyle.color = 'red'
            this.fontStyle.fontSize = '50px'
        }
    }
}
</script>

<style scoped>
h1 {
    margin: 0;
}
.active {
    color: red;
    font-weight: bold;
}
</style>
