<template>
    <!-- submit.prevent form의 기본동작 새로고침을 막음 -->
  <form v-on:submit.prevent="submitForm"> 
    <div>
        <label for="username">id : </label>
        <input id="username" type="text" v-model="username">
    </div>
    <div>
        <label for="password">pw : </label>
        <input id="password" type="text" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
    // 컴포넌트간 data의 참조가 일어나지않게 새객체를 리턴해줌
    data: function() { 
        return {
            username:'',
            password:'',
        }
    },
    methods:{
        submitForm: function() {
            var url = 'https://jsonplaceholder.typicode.com/users';
            var data = {
                username: this.username,
                password: this.password,
            }
            axios.post(url,data)
                .then(function(res) {
                    console.log(res);
                })
                .catch(function(error) {
                    console.error(error);
                });
        }
    }
}
</script>

<style>

</style>