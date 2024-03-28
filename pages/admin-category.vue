<template>
    <Header /> <!-- 헤더 컴포넌트 불러오기 -->
    <div class="content-wrap">
      <SideNav /> <!-- 사이드 네비게이션 컴포넌트 불러오기 -->
      <div class="content">
        <div class="ct-title">
            <h3>카테고리 관리</h3>
        </div>
        <div class="ct-wrap">
            <div>
                <ul>
                    <li v-for="category in categories" :key="category.id">{{ category.name }}</li>
                </ul>
                <button @click="showCategorySettings = true">+카테고리 추가</button>
            </div>
            <div class="ct-setting">
                    <div v-if="showCategorySettings">
                    <CategorySettings @save="addCategory" />
            </div>
            </div>
        </div>
      </div>
    </div>
</template>

<script>
    import Header from '@/layouts/Header.vue';
    import SideNav from '@/layouts/SideNav.vue';
    import CategorySettings from '@/components/CategorySettings.vue';

    export default {
        data() {
          return {
            categories: [
                { id: 1, name: '공지사항' },
                { id: 2, name: '자유게시판' },
                ],
                showCategorySettings: false,
            }
  },

    components: {
        Header,
        SideNav,
        CategorySettings,
     },

     methods: {
                addCategory(newCategoryName) {
            // 새로운 카테고리 객체 생성
            const newCategory = {
                id: this.categories.length + 1,
                name: newCategoryName
            };
            // 새로운 카테고리를 배열에 추가
            this.categories.push(newCategory);
            // 상위 컴포넌트에서 백엔드로 카테고리 정보 전송하는 로직 구현
            // 백엔드에서 처리 후 추가된 카테고리 정보를 받아와서 화면에 업데이트하는 로직 구현
            // 예시로 alert를 이용하여 추가된 카테고리 이름을 출력
            alert(`새로운 카테고리가 추가되었습니다: ${newCategoryName}`);
            // 카테고리 설정 컴포넌트를 닫음
            this.showCategorySettings = false;
        }
     }
    }
</script>

