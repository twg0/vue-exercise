<template>
    <!--  .prevent 를 통해 기본 동작을 막을 수 있음  -->
    <!--  .once 는 handler 메소드를 단 한 번만 동작시킴  -->
    <!--  체이닝 형태로 사용할 수 있음  -->
    <!--  .prevent.once : 처음 눌렀을 때는 기본 동작 막기, 두 번째 누를때는 기본동작은 하되 handler는 한 번만 호출  -->
    <a
        href="https://naver.com"
        target="_blank"
        @click.prevent.once="handler">
        NAVER
    </a>

<!--  child를 클릭한다는 것은 parent에 포함된 child를 클릭하는 것이기 때문에 child클릭 -> child 동작 -> parent 동작 이렇게 된다.(이벤트버블링)  -->
<!--  .stop을 통해 propagation을 막을 수 있다.  -->
<!--  반대로 부모 요소에서 자식 요소로 내려오는 것을 capturing 이라고 한다.  -->
    <div
        class="parent"
        @click="handlerA">
        <div
            class="child"
            @click.stop="handlerB"></div>
    </div>

    <div
        class="parent"
        @click.capture="handlerA">
        <div
            class="child"
            @click="handlerB"></div>
    </div>

<!--  .self 해당 영역을 정확하게 클릭했을 때만 이벤트가 동작  -->
<!--  target과 currentTarget이 같을 때 동작  -->
    <div
        class="parent"
        @click.self="handlerA">
        <div
            class="child"></div>
    </div>

<!--  로직과 스크롤을 동시에 처리하기 때문에 부하가 크게 걸림  -->
<!--  .passive를 통해 처리되는 로직과 스크롤을 분리하여 적용  -->
    <div
        class="parent2"
        @wheel.passive="handler">
        <div
            class="child2"></div>
    </div>
</template>

<script>

export default {
    methods: {
        handler(event) {
            // event.preventDefault(); // 기본동작을 방지한다는 의미, html에 들어있는 하이퍼링크 기능을 동작시키지 않는 메소드

            // 큰 부하를 거는 코드
            for (let i = 0; i < 10000; i++) {
                console.log(event);
            }
        },
        handlerA(event) {
            console.log(event.target) // 클릭한 부분
            console.log(event.currentTarget) // 클릭에 대한 이벤트가 붙어있는 부분
            console.log('A');
        },
        handlerB() {
            // event.stopPropagation(); // event의 전파(버블링)를 방지한다.
            console.log('B');
        }
    }
}
</script>

<style scoped lang="scss">
.parent {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;

    .child {
        width: 100px;
        height: 100px;
        background-color: orange;
    }
}

.parent2 {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    overflow: auto; // 크기를 벗어나면 스크롤 바가 생긴다.
    .child2 {
        width: 100px;
        height: 2000px;
        background-color: orange;
    }
}
</style>
