<template>
    <div class="postTitle">
        <div>
            <h2>게시글 관리</h2>
            <span>{{ postCount }}</span>
        </div>
        <div>
            <button>글쓰기</button>
        </div>
    </div>
    <div class="option-tap">
        <input type="checkbox" class="option-check" v-model="isChecked" @change="handleChange">
        <q-btn-dropdown label="변경" class="q-button-style">
            <q-list>
                <q-item clickable v-close-popup @click="onItemClick">
                <q-item-section>
                    <q-item-label>공개</q-item-label>
                </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                <q-item-section>
                    <q-item-label>비공개</q-item-label>
                </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                <q-item-section>
                    <q-item-label>삭제</q-item-label>
                </q-item-section>
                </q-item>
            </q-list>
        </q-btn-dropdown>
    </div>

</template>

<script>
export default {
  props: {
    postCount: {
      type: Number,
      required: true
    },
    posts: {
      type: Array,
      default: () => []
    },
  },
  data() {
    return {
      checked: false,
    };
  },
  isChecked: {
      type: Boolean,
      required: true
    },

  methods: {
        handleChange() {
      this.$emit('checkboxChange', this.isChecked);
    }
  }
};
</script>