<template>
  <form action="">
    <div>
        <label for="username">id : </label>
        <input id="username" type="text" v-model="username">
    </div>
    <div>
        <label for="password">pw : </label>
        <input id="password" type="text">
    </div>
    <button>login</button>
  </form>
</template>

<script>
export default {
    // 컴포넌트간 데이터의 참조가 일어나지않게 새객체를 리턴해줌
    data: function() { 
        return {
            username:'',
            password:''
        }
    }
}
</script>

<style>

</style>