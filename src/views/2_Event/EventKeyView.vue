<template>
  <div><!-- v-model로 양방향 바인딩  keyup이벤트를 사용해 checkEnter 함수를 확인한다.event를 보낸다.-->
    <input type="search" v-model="searchText" @keyup="checkEnter($event)">
    <button @click="doSearch">조회1</button>
    <!-- vue에서는 @keyup.enter로 바로 확인할 수 있다 -->
    <input type="search" v-model="searchText" @keyup.enter="doSearch">
    <button @click="doSearch">조회2</button>
  </div>
</template>
<script>

export default {
  components: {},
  data() {
    return {
      sampleData: '*'
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    doSearch() {
      console.log(this.searchText)
    },
    checkEnter(event) { // event를 받아주고
      if (event.keyCode === 13) { // 받은 keyup이벤트가(누른 키가) 13(엔터)가 맞다면
        this.doSearch() // doSearch함수를 호출하라
      }
    }
  }
}
</script>
<style scoped>

</style>
