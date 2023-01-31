<template>
  <div>
    <select name="" id="" v-model="selectdCity">
      <option value="">선택</option>
      <option value="02">서울</option>
      <option value="031">경기</option>
      <option value="051">부산</option>
    </select>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      selectdCity: '02'
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
