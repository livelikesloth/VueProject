<template>
  <div>
    <!-- v-bind를 사용해 요소를 직접 바인딩 -->
    <input type="text" v-bind:value="userId" readonly />
    <!-- v-bind 생략 -->
    <input type="text" :value="userId" readonly />
    <br />
    <!-- :src 로 요소를 직접 바인딩 -->
    <img :src="imgSrc" alt="" style="width: 300px; height: auto" />
    <br />
    <!-- 어떤 값이라도 무조건 들어와야 하는 searchbar -->
    <input type="search" v-model="txt1" />
    <!-- searchbar에 입력이 안되어 있으면 버튼 비활성화  v-model로 양방향 바인딩이 된 txt1이 비어있냐?-->
    <button :disabled="txt1 === ''">조회</button>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      userId: 'Sloth',
      imgSrc: 'https://ichef.bbci.co.uk/images/ic/1008xn/p07rdf0q.jpg',
      txt1: ''
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
<style scoped></style>
