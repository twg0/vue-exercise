<template>
    <!--  export default 의 data 영역에서 html 방향으로만 데이터가 연결되기 때문에 단방향 바인딩이라고 함  -->
<!--  @input 이벤트를 통해 handler가 동작하며 msg의 값을 변경하고 그 값이 다시 html로 돌아와 반응성에 의해 출력됨, 서로 영향을 주는 양방향 데이터 바인딩이 발생 -->
    <h1>{{ msg }}</h1>
    <input
        type="text"
        :value="msg"
        @input="handler">
<!--  인라인으로 작성할 수 있음  -->
    <input
        type="text"
        :value="msg"
        @input="msg = $event.target.value">
<!--  더 간소화할 수 있음  -->
    <input
        type="text"
        v-model="msg">
    <h1>{{ checked}}</h1>
    <input
        type="checkbox"
        v-model="checked">
<!--  v-model 주의사항 : 한글은 자음과 모음으로 한 글자 만들어져야 적용됨, 이때는 인라인 형태로 하는 것이 바로바로 적용됨  -->
</template>

<script>

export default {
    data() {
        return {
            msg: 'Hello world!',
            checked: false
        }
    },
    methods: {
        handler(event) {
            console.log(event.target.value);
            this.msg = event.target.value;
        }
    }

}
</script>

