<!-- CategorySettings.vue -->
<template>
    <div class="settingWrap">
        <form @submit.prevent="saveCategory">
      <div class="form-group">
        <label for="categoryName">카테고리명</label>
        <input type="text" id="categoryName" v-model="categoryName" required>
      </div>
      <div class="form-group">
        <label for="categoryPermission">권한 설정</label>
        <select id="categoryPermission" v-model="categoryPermission" required>
          <option value="public">전체 공개</option>
          <option value="private">비공개</option>
        </select>
      </div>
      <!-- 다른 설정 항목 추가 -->
      <div class="form-group">
        <button type="submit">저장하기</button>
        <button type="button" @click="cancel">취소</button>
      </div>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newCategoryName: '' // 사용자가 입력한 새로운 카테고리 이름을 저장할 데이터
      };
    },
    methods: {
      saveCategory() {
        // 새로운 카테고리 정보를 상위 컴포넌트로 전달
        this.$emit('save', this.newCategoryName);
      }
    }
  };
  </script>
  