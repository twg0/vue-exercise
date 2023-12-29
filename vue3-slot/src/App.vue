<template>
    <MyBtn>
        <!--    slot에 직접 위치를 지정, 그래서 순서가 바뀌어도 괜찮음    -->
        <!--    v-slot: 은 #으로 약어 사용 가능    -->
        <template #text>
            <span>Banana</span>
        </template>
        <template #icon>
            <span>(B)</span>
        </template>
        <!--    여기에 있는 모든 내용이 slot을 대체하여 들어가게 됨    -->
        <!--        <span>Banana</span>-->
        <!--        <span>(B)</span>-->
    </MyBtn>
</template>

<script>

import MyBtn from "@/components/MyBtn.vue";

export default {
    components: {MyBtn}
}
</script>
