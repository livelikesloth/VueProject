<template>
  <div>
    <!-- 도시 select -->
    <!-- 시티를 선택할때마다(change) selectedCity에 값을 보낸다(양방향 바인딩) -->
    <select @change="changeCity" v-model="selectedCity">
      <option value="">==도시선택==</option>
      <!--
        v-for를 사용해 cityList에 있는 값을 뿌려주고 각각을 city로 명한다.
        v-bind를 사용해 value 속성에 city.cityCode에 해당하는 city를 가져온다.
        v-bind를 사용해 유니크한 key속성을 city.cityCode에서 부여한다.
      -->
      <option
        :value="city.cityCode"
        :key="city.cityCode"
        v-for="city in cityList"
      >
      <!-- 각각 담긴 city에서 title만 뽑아 출력한다. -->
        {{ city.title }}
      </option>
    </select>
    <!-- 동 select -->
    <select>
      <!--
        v-for를 사용해 선택된 도시에 해당하는 동들을 불러오고 각각을 dong에 담는다.
        v-bind 를 사용해 value에 dongCode를 담는다.
        v-bind 를 사용해 유니크한 키값 dongCode를 담는다.
      -->
      <option
        :value="dong.dongCode"
        :key="dong.dongCode"
        v-for="dong in dongListFromSelectedCity"
      >
        {{ dong.dongTitle }}
      </option>
    </select>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      selectedCity: '', // 사용자가 선택한 city가 이곳에 들어감
      dongListFromSelectedCity: [], // 사용자가 선택한 city에 해당하는 dongList들이 들어감
      cityList: [
        { cityCode: '02', title: '서울' },
        { cityCode: '031', title: '경기' },
        { cityCode: '051', title: '부산' }
      ],
      dongList: [
        // cityCode로 걸러내서 dongCode와 dongTitle을 반환함
        { cityCode: '02', dongCode: '1', dongTitle: '서울1동' },
        { cityCode: '02', dongCode: '2', dongTitle: '서울2동' },
        { cityCode: '02', dongCode: '3', dongTitle: '서울3동' },
        { cityCode: '02', dongCode: '4', dongTitle: '서울4동' },
        { cityCode: '031', dongCode: '1', dongTitle: '경기1동' },
        { cityCode: '031', dongCode: '2', dongTitle: '경기2동' },
        { cityCode: '031', dongCode: '3', dongTitle: '경기3동' },
        { cityCode: '031', dongCode: '4', dongTitle: '경기4동' },
        { cityCode: '051', dongCode: '1', dongTitle: '부산1동' },
        { cityCode: '051', dongCode: '2', dongTitle: '부산2동' },
        { cityCode: '051', dongCode: '3', dongTitle: '부산3동' },
        { cityCode: '051', dongCode: '4', dongTitle: '부산4동' }
      ]
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    changeCity() {
      // dong.cityCode가 사용자가 선택한 cityCode와 같은 데이터를 뽑아온다.
      this.dongListFromSelectedCity = this.dongList.filter(
        (dong) => dong.cityCode === this.selectedCity
      )
    }
  }
}
</script>
<style scoped></style>
