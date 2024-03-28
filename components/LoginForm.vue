<template>
    <div class="LoginFormContents">
        <div class="LoginWrap">
            <div class="LoginTitle">
                <h1>WITHCHAT</h1>
                <p>로그인하세요</p>
            </div>
            <form class="LoginForm" @submit.prevent="handleSubmit">
            <div class="form-group">
                <input type="email" id="email" v-model="email" placeholder="Email" required>
            </div>
            <div class="form-group">
                <input type="password" id="password" v-model="password" placeholder="Password" required>
            </div>
            <button type="submit">로그인</button>
            </form>
            <div class="SignIn">
                <p>WITHCHAT이 처음이세요? <NuxtLink to="/company-registration">회사등록</NuxtLink></p>
            </div>
            
        </div>
    </div>
</template>


<script>
  export default {
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    async handleSubmit() {
      // 여기서 실제로 로그인 폼을 제출하는 로직을 작성합니다.
      // 로그인이 성공하면 네비게이션의 첫 번째 페이지로 이동합니다.
      try {
        // 로그인 처리 코드...

        // 로그인이 성공했을 때 네비게이션의 첫 번째 페이지로 이동합니다.
        await this.$router.push('/admin-board'); 
      } catch (error) {
        console.error('로그인에 실패했습니다.', error);
        // 로그인 실패 시에 대한 처리 코드를 작성합니다.
      }
    }
  }
};
</script>

<style>

</style>