<template>
    <Header /> <!-- 헤더 컴포넌트 불러오기 -->
    <div class="content-wrap">
      <SideNav /> <!-- 사이드 네비게이션 컴포넌트 불러오기 -->
      <div class="content">
        <PostTitle :postCount="posts.length" :isChecked="isChecked" @checkboxChange="handleCheckboxChange" />
        <PostList :posts="posts" :isChecked="isChecked" />
      </div>
    </div>
</template>

<script>
    import Header from '@/layouts/Header.vue';
    import SideNav from '@/layouts/SideNav.vue';
    import PostTitle from '@/components/PostTitle.vue'; 
    import PostList from '@/components/PostList.vue'; 

    export default {
        data() {
          return {
            posts: [ // 게시글 데이터 배열
              { id: 1, title: '업데이트 관련 공지사항', content: '공지사항', name: '송수련', date:'2024.3.12', comment: 2 },
              { id: 2, title: '안녕하세요 오늘 저녁 메뉴 추천좀요', content: '자유게시판', name: '송수련', date:'2024.3.12', comment: 0},
              { id: 3, title: '헬스 동반 할인 같이 받으실 분 있나욧', content: '자유게시판', name: '송수련', date:'2024.3.12', comment: 785},
              { id: 4, title: '간식 관련 안내', content: '공지사항', name: '송수련', date:'2024.3.12', comment: 30 }
            ],
            postCount: 4,
            isChecked : false
                }
  },

    components: {
        Header,
        SideNav,
        PostTitle,
        PostList,
     },

     methods: {
      handleCheckboxChange(isChecked) {
      this.isChecked = isChecked
        }
     }
    };
</script>

