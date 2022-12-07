<template>
  <div id="HappyLunchPage">
    <span class="title">점심시간 식당 뽑기 👉 </span>
    <button @click="picking()">뽑기</button>
    <div v-if="selectedRestaurant1 !== ''">
      <br />
      <h3>👩‍🍳 결과</h3>
      <div>🍜 {{ selectedRestaurant1 }}</div>
      <div>🍟 {{ selectedRestaurant2 }}</div>
      <div>🍣 {{ selectedRestaurant3 }}</div>
      <div>🍱 {{ selectedRestaurant4 }}</div>
      <div>🍖 {{ selectedRestaurant5 }}</div>
      <div>🥗 {{ selectedRestaurant6 }}</div>
      <div>🍘 {{ selectedRestaurant7 }}</div>
      <br />
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
          { name: '화담면옥', type: '한식', distance: '도보' },
          { name: '댓끼리짬뽕', type: '중식', distance: '5m' },
          { name: '윳쿠리', type: '일식', distance: '15m' },
          { name: '등촌', type: '한식', distance: '7m' },
          { name: '두마리찜닭', type: '한식', distance: '10m' },

          { name: '만민칼국수', type: '면식', distance: '7m' },
          { name: '팔도비빔밥', type: '한식', distance: '3m' },
          { name: '뜨돈', type: '일식', distance: '10m' },
          { name: '수가성', type: '한식', distance: '7m' },
          { name: '온정가', type: '한식', distance: '15m' },

          { name: '육대장', type: '한식', distance: '5m' },
          { name: '이유있는 갈비찜', type: '한식', distance: '15m' },
          { name: '김치찌개', type: '한식', distance: '10m' },
          { name: '꿀꿀촌', type: '한식', distance: '도보' },
          { name: '가정초밥', type: '일식', distance: '15m' },

          { name: '춘천닭갈비', type: '한식', distance: '5m' },
          { name: '버거킹', type: '양식', distance: '10m' },
          { name: '맥도날드', type: '양식', distance: '7m' },
          { name: '바보형제쭈꾸미', type: '한식', distance: '10m' },
          { name: '한티재', type: '한식', distance: '10m' },

          { name: '장사이야기:포', type: '아시안', distance: '5m' },
          { name: '아비꼬', type: '일식', distance: '7m' },
          { name: '리돈까스', type: '일식', distance: '10m' },
          { name: '홍익돈까스', type: '일식', distance: '7m' },
          { name: '곤지곤지', type: '한식', distance: '7m' },

          { name: '왕돌잠', type: '일식', distance: '15m' },
          { name: '동인동양푼이갈비찜', type: '한식', distance: '10m' },
          { name: '영일궁', type: '한식', distance: '7m' },
          { name: '한촌돼지국밥', type: '한식', distance: '15m' },
          { name: '효자동곱닭', type: '한식', distance: '10m' },

          { name: '정직유부', type: '한식', distance: '8m' },
          { name: '아리랑감자탕', type: '한식', distance: '10m' },
          { name: '타마시텐', type: '일식', distance: '7m' },
          { name: '어탕', type: '한식', distance: '10m' },
        ],
        // 스페셜, 자주 안가는 애들
        special: [
          { name: '다모리', type: '한식', distance: '10m' },
          { name: '불미골', type: '한식', distance: '15m' },
          { name: '범촌매운탕', type: '한식', distance: '20m' },
          { name: '마라탕', type: '중식', distance: '10m' },
          { name: '호원', type: '중식', distance: '10m' },
        ],
      },

      selectedRestaurant1: '',
      selectedRestaurant2: '',
      selectedRestaurant3: '',
    }
  },
  mounted() {},
  methods: {
    rand(min, max) {
      return Math.floor(Math.random() * (max - min)) + min
    },
    picking() {
      // idx 3개 뽑기
      const idx1 = this.rand(0, 5)
      const idx2 = this.rand(5, 10)
      const idx3 = this.rand(10, 15)
      const idx4 = this.rand(15, 20)
      const idx5 = this.rand(20, 25)
      const idx6 = this.rand(25, 30)
      const idx7 = this.rand(30, 34)

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
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx4) {
          this.selectedRestaurant4 = restaurant.name
        }
      })
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx5) {
          this.selectedRestaurant5 = restaurant.name
        }
      })
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx6) {
          this.selectedRestaurant6 = restaurant.name
        }
      })
      this.restaurantList.normal.forEach((restaurant, idx) => {
        if (idx === idx7) {
          this.selectedRestaurant7 = restaurant.name
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
