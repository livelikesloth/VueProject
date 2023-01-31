<template>
  <div>
    <!--
      클래스에 오브젝트를 선언해서 넣을 수 있다. 변수를 설정해 동적으로 만들 수 있다.
      키는 클래스 이름, 값은 불리언
      클래스 명이 한단어로 되어있으면 따옴표 안붙여도 됨
    -->
    <div :class="{ 'text_navy':hasError, 'active':isActive }">클래스 바인딩</div>
    <!-- 배열로도 가능 -->
    <div :class="class2">클래스 바인딩2</div>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      isActive: false,
      hasError: false,
      class2: ['active', 'hadError']
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
<style scoped>
  .active{
    font-weight: bolder;
    border: 1px solid black;
  }
  .text_navy{
    background-color: yellow;
    color: navy;
  }
</style>
