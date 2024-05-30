<template>
    <header>
        <h5>------AppHeader start--------</h5>
        <p>props : {{ propsname }}</p>
        <p>props : {{ propsname2 }}</p>
        <button v-on:click="sendEvent">send</button>
        <h5>------AppHeader end--------</h5>
    </header>
</template>

<script>
export default {
    props: ['propsname','propsname2'],
    // props: {
    //     이름:타입
    // }
    methods: {
        sendEvent: function() {
            this.$emit('renew')
        // 이벤트 받는곳 : app-header 태그를 호출한 부모태그의 v-on:renew
        }
    }
}
</script>

<style>

</style>