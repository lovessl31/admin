<template>
    <div>
        <div class="RegisterContents">
            <div class="RegisterTitle">
                <h2>회사 정보 등록</h2>
                <p>아래 양식에 회사 정보를 입력해주세요.</p>
            </div>
            <div class="RegisterWrap">
                <form @submit.prevent="handleSubmit" class="RegisterFrom">
                <div class="register-form-group">
                    <label for="businessRegistrationNumber">사업자 등록번호</label>
                    <input type="text" id="businessRegistrationNumber" v-model="businessRegistrationNumber" required>
                </div>
                <div class="register-form-group">
                    <label for="companyName">회사명</label>
                    <input type="text" id="companyName" v-model="companyName" required>
                </div>
                <div class="register-form-group">
                    <label for="representativeName">대표자명</label>
                    <input type="text" id="representativeName" v-model="representativeName" required>
                </div>
                <div class="form-group-file">
                    <label for="business_registration_certificate" class="file-input-label" @click.stop>사업자등록증</label>
                    <input ref="fileInput" type="file" id="business_registration_certificate" name="business_registration_certificate" accept="image/*,.pdf" style="display: none;" @change="displayFileName">
                    <div class="file-content">
                        <div class="display" id="file-name-display" :title="uploadedFileName">{{ uploadedFileName }}</div>
                        <div class="file-attach" ref="inputFile" @click="displayFileInput">
                            <span>파일첨부</span>
                        </div>
                    </div>
                </div>
                </form>
            </div>
            <button class="register-submit" type="submit">등록</button>
        </div>
    </div>
</template>

<script>
  export default {
  data() {
    return {
      businessRegistrationNumber: '',
      companyName: '',
      representativeName: '',
      businessRegistrationProof: null,
      uploadedFileName: ''
    };
  },
  methods: {
        handleSubmit() {
        // 폼 제출 로직을 구현합니다.
        },
        displayFileInput() {
        this.$refs.fileInput.click(); // 파일 입력 클릭 이벤트 실행
        },
        displayFileName(event) {
            const fileName = event.target.files[0].name; // 파일명 가져오기
            this.uploadedFileName = fileName; // 파일명 업데이트
        }
    }
};

</script>

<style lang="scss" scoped>

</style>