<template>
  <div>
    <!-- data함수 안에서 message키와 userName키를 사용해 데이터 가져오기 -->
    <h1> {{message}} {{userName}} How are you?</h1>
    <p>{{message2}}</p>
  </div>
</template>
<script>
export default {
  data () {
    return {
      userName: 'Sloth',
      message: 'Hi! 반가워요 !',
      message2: '안녕안녕안녕~'
    }
  }
}
</script>
<style scoped>
  .text-red{
    color: red;
  }
</style>
