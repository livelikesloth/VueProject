<template>
  <div>
    <input type="text" v-model="userId" />
    <button @click="myFunction">클릭</button>
    <button @click="changeData">변경</button>
    <br>
    <!-- string으로 더해져서 num1값과 num2값이 옆으로 붙은 값이 나온다 ex num1='1'+num2='2' result:12 -->
    <input type="text" v-model="num1" />+
    <input type="text" v-model="num2" />=
    <span>{{num1+num2}}</span>
    <br>
    <!-- v-model.number를 사용해 string값을 number로 바꿔준다. 산술연산이 된다. -->
    <input type="text" v-model.number="num3" />+
    <input type="text" v-model.number="num4" />=
    <span>{{num3+num4}}</span>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      userId: 'SLOTH',
      num1: 0,
      num2: 0,
      num3: 0,
      num4: 0
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    myFunction() {
      console.log(this.userId) // this키워드를 사용해서 object안의 특정 키값을 불러오기
    },
    changeData() {
      this.userId = 'Yuki'
    }
  }
}
</script>
<style scoped>

</style>
