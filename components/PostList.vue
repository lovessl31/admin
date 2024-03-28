<template>
    <ul class="postList">
      <li v-for="post in reversedPosts" :key="post.id" class="postItem">
        <div class="post-left">
          <input type="checkbox" class="option-check" :checked="isChecked" @change="handleItemClick"/>
          <div>
            <h3>{{ post.title }}</h3>
            <span>{{ post.content }}</span>
            <span>{{ post.name }}</span>
            <span>{{ post.date }}</span>
            <span v-if="post.comment !== 0">댓글 {{ post.comment }}</span>
          </div>
        </div>
        <div class="post-right">
          <button>수정</button>
          <button>삭제</button>
        </div>
      </li>
    </ul>
  </template>
  
  <script>
import { mdiConsoleNetworkOutline } from '@quasar/extras/mdi-v4';

  export default {
    data() {
      return {
        isChecked: false,
        items: [ 'item1', 'item2', 'item3'],
      }
    },
    computed: {
    reversedPosts() {
      // 배열을 복제하고 역순으로 정렬하여 반환
      return this.posts.slice().reverse();
    }
  },
    methods : {
      handleItemClick() {
        console.log(this.isChecked ? 'All items selected' : 'All items deselected')
      },
    },
    props: {
      posts: {
        type: Array,
        default: () => []
      },
      isChecked: {
      type: Boolean,
      required: true
    }
    },

  };
  </script>