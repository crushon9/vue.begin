<template>
  <!-- template 아래에는 하나의 상위 태그만 있어야함 -->
  <div>
    <h1>vue-cli : Command Line Interface</h1>
    <h5>------App start--------</h5>
    <p>{{ parentdata }}</p>
    <p>{{ parentdata2 }}</p>
    <app-header v-bind:propsname="parentdata" v-bind:propsname2="parentdata2" v-on:renew="renewData" />
    <h5>------App end--------</h5>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'

export default {
  // 객체 리터럴방식으로 쓰면 new Vue()로 만든값과 충돌할수있기때문에
  // export default에서는 함수 리턴으로 값을 넣음
  data: function() {
    return {
      parentdata: 'data from app.vue',
      parentdata2: 'parentdata',
      cnt:0
    }
  },
  components: {
    'app-header':AppHeader,
  },
  methods: {
    renewData: function() {
      this.parentdata2 = '"renew" event $emit by <AppHeader> X '+ (++this.cnt)
    }
  }
}
</script>

<style>

</style>