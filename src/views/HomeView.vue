<template>
  <div class="container">
    <!-- 팝업 열기 버튼 -->
    <button @click="openPopup">팝업 오픈!</button>
    <p>팝업 버튼</p>
    <!-- About 페이지로 이동하는 링크 -->
    <router-link to="/about" class="clickable">메인 페이지 이미지 페이지</router-link>
    
    <!-- 일반 팝업 컴포넌트 -->
    <div v-if="isPopupOpen" class="popup">
      <div class="popup-content">
        <!-- 팝업 상단의 랜덤 이미지 -->
        <div class="popup-icon"><img src="https://picsum.photos/50/50" alt="랜덤 이미지"></div>
        
        <!-- 팝업 내용 및 닫기 버튼 -->
        <div>
        <p>팝업입니다</p>
        <button @click="closePopup">닫기</button>
        </div>
      </div>
    </div>

    <!-- 이미지 페이지 팝업 컴포넌트-->
    <div v-if="isImagePopupOpen" class="popup">
      <div class="popup-content">
        <h2>이미지 페이지</h2>
        <img src="https://via.placeholder.com/300x200" alt="샘플 이미지" />
        <button @click="closeImagePopup">닫기</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPopupOpen: false,
      isImagePopupOpen: false
    }
  },
  methods: {
    // 일반 팝업 열기
    openPopup() {
      this.isPopupOpen = true
    },
    // 일반 팝업 닫기
    closePopup() {
      this.isPopupOpen = false
    },
    // 이미지 팝업 열기 
    openImagePopup() {
      this.isImagePopupOpen = true
    },
    // 이미지 팝업 닫기 
    closeImagePopup() {
      this.isImagePopupOpen = false
    }
  }
}
</script>

<style scoped>
/* 컨테이너 스타일 */
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 50px;
  text-align: center;
}

/* 팝업 배경 스타일 */
.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

/* 팝업 내용 스타일 */
.popup-content {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
  width: 800px;
  text-align: center;
}

/* 팝업 아이콘(이미지) 스타일 */
.popup-icon {
  display: flex;
  justify-content: flex-end;
  font-size: 24px;
  margin-bottom: 10px;
}

/* 클릭 가능한 요소 스타일 */
.clickable {
  cursor: pointer;
  color: blue;
  text-decoration: underline;
}

/* 이미지 스타일 */
img {
  max-width: 100%;
  height: auto;
  margin-right: 10px;
  border-radius: 5px;
}
</style>