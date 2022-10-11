<template>
  <div id="HappyLunchPage">
    <div class="title">점심시간 식당 뽑기 ㅎㅎ</div>
    <button @click="picking()">뽑기</button>
    <div
      v-if="
        selectedRestaurant1 !== '' ||
        selectedRestaurant1 !== '' ||
        selectedRestaurant1 !== ''
      "
    >
      <div>오늘 점심은~~~</div>
      <div>식당1: {{ selectedRestaurant1 }}</div>
      <div>식당2: {{ selectedRestaurant2 }}</div>
      <div>식당3: {{ selectedRestaurant3 }}</div>
      <button v-if="rePickingCnt > 0" @click="rePicking()">다시 뽑기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HappyLunchPage',
  data() {
    return {
      rePickingCnt: 1,

      restaurantList: {
        normal: [
          { name: '육대장', type: '한식', distance: '5m' },
          { name: '만민칼국수', type: '면식', distance: '7m' },
          { name: '화담면옥', type: '한식', distance: '도보' },
          { name: '윳쿠리', type: '일식', distance: '15m' },
          { name: '어탕', type: '한식', distance: '10m' },
          { name: '댓끼리짬뽕', type: '중식', distance: '5m' },
          { name: '팔도비빔밥', type: '한식', distance: '3m' },
          { name: '두마리찜닭', type: '한식', distance: '10m' },
          { name: '뜨돈', type: '일식', distance: '10m' },
          { name: '수가성', type: '한식', distance: '7m' },
          { name: '김치찌개', type: '한식', distance: '10m' },
          { name: '마라탕', type: '중식', distance: '10m' },
          { name: '장사이야기:포', type: '아시안', distance: '5m' },
          { name: '꿀꿀촌', type: '한식', distance: '도보' },
          { name: '아리랑감자탕', type: '한식', distance: '10m' },
          { name: '춘천닭갈비', type: '한식', distance: '5m' },
          { name: '버거킹', type: '양식', distance: '10m' },
          { name: '맥도날드', type: '양식', distance: '7m' },
          { name: '아비꼬', type: '일식', distance: '7m' },
          { name: '리돈까스', type: '일식', distance: '10m' },
          { name: '홍익돈까스', type: '일식', distance: '7m' },
          { name: '곤지곤지', type: '한식', distance: '7m' },
          { name: '등촌', type: '한식', distance: '7m' },
          { name: '왕돌잠', type: '일식', distance: '15m' },
          { name: '정직유부', type: '한식', distance: '8m' },
          { name: '동인동양푼이갈비찜', type: '한식', distance: '10m' },
          { name: '영일궁', type: '한식', distance: '7m' },
          { name: '한촌돼지국밥', type: '한식', distance: '15m' },
          { name: '응급실떡볶이', type: '한식', distance: '5m' },
          { name: '한티재', type: '한식', distance: '10m' },
          { name: '샌드비치', type: '양식', distance: '10m' },
          { name: '호원', type: '중식', distance: '10m' },
          { name: '바보형제쭈꾸미', type: '한식', distance: '10m' },
          { name: '효자동곱닭', type: '한식', distance: '10m' },
          { name: '한양곱창전골', type: '한식', distance: '10m' },
          { name: '타마시텐', type: '일식', distance: '7m' },
          { name: '가정초밥', type: '일식', distance: '15m' },
        ],
        special: [
          { name: '다모리', type: '한식', distance: '10m' },
          { name: '불미골', type: '한식', distance: '15m' },
          { name: '범촌매운탕', type: '한식', distance: '20m' },
        ],
      },

      selectedRestaurant1: '',
      selectedRestaurant2: '',
      selectedRestaurant3: '',
    }
  },
  mounted() {},
  methods: {
    picking() {
      // idx 3개 뽑기
      const idx1 = Math.floor(Math.random() * 10)
      const idx2 = Math.floor(Math.random() * 10) + 20
      const idx3 =
        Math.floor(Math.random() * (this.restaurantList.normal.length - 30)) +
        30

      // 중복 체크
      // 식당 뽑기
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx1) {
          this.selectedRestaurant1 = restaurant.name
        }
      })
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx2) {
          this.selectedRestaurant2 = restaurant.name
        }
      })
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx3) {
          this.selectedRestaurant3 = restaurant.name
        }
      })
    },
    rePicking() {
      this.picking()
      this.rePickingCnt--
    },
  },
}
</script>

<style lang="scss" scoped></style>
