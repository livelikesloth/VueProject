<template>
  <div>
    <!-- 마치 오브젝트 키:밸류 를 보는 것 같다. -->
    <div style="color:red;font-size:30px">스타일 바인딩: 글씨는 red, 폰트크기:30px</div>
    <!-- 그럼 오브젝트로 적용하자! -->
    <div :style="style1"> 스타일 바인딩: 글씨는 green, 폰트크기:30px</div>
    <button @click="style1.color='blue'">색상 바꾸기</button>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      style1: {
        color: 'green',
        fontSize: '30px' // 카멜케이스를 써야한다.
      }
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

</style>
