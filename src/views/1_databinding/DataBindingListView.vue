<template>
  <div>
    <div>
      <select name="" id="">
        <!--
          옵션이 cities의 갯수만큼 존재해야 한다. v-for를 사용한다.
          for in 사용하는 것 처럼 city in cities로 사용하는데
          cities의 데이터에서 뽑아온 각각의 오브젝트데이터가 city로 저장되는 것
          유니크한 key를 무조건 잡아주어야 한다. 여기서는 code가 유일한 키값이 된다. city의 code
          보여주는 화면에는 city의 title을 보여준다.
        -->
        <option value=""></option>
        <option value="" :key="city.code" v-for="city in cities">{{city.title}}</option>
      </select>
    </div>
    <div>
      <table>
        <thead>
          <tr>
            <th>제품번호</th>
            <th>제품명</th>
            <th>가격</th>
            <th>주문수량</th>
            <th>합계</th>
          </tr>
        </thead>
        <tbody>
          <tr :key="drink.drinkId" v-for="drink in drinkList">
            <td>{{drink.drinkId}}</td>
            <td>{{drink.drinkName}}</td>
            <td>{{drink.price}}</td>
            <td><input type="number" v-model="drink.qty"></td>
            <td>{{drink.price * drink.qty}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      cities: [
        { title: '서울', code: '02' },
        { title: '경기', code: '031' },
        { title: '부산', code: '051' }
      ],
      drinkList: [
        { drinkId: '1', drinkName: '코카콜라', price: 700, qty: 1 },
        { drinkId: '2', drinkName: '오렌지주스', price: 1200, qty: 1 },
        { drinkId: '3', drinkName: '커피', price: 500, qty: 1 },
        { drinkId: '4', drinkName: '물', price: 700, qty: 1 },
        { drinkId: '5', drinkName: '보리차', price: 1200, qty: 1 },
        { drinkId: '6', drinkName: '포카리', price: 1000, qty: 1 },
        { drinkId: '7', drinkName: '뽀로로', price: 1300, qty: 1 }
      ]
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
