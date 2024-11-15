<script>
import CommentItem from './CommentItem.vue';

export default {
  components: {
    CommentItem
  },
  data() {
    return {
      comments: [
        { username: 'Abrar', comment: 'Bang Absen Bang', date: '2024-09-16' },
        { username: 'Ramadava', comment: 'Aku Telat ga bang', date: '2024-09-16' },
        { username: 'Algadri', comment: 'Bang dijawa ada NAGA.', date: '2024-09-16' }
      ],
      newUsername: '',
      newComment: '',
      newDate: ''
    };
  },
  methods: {
    addComment() {
      const newComment = {
        username: this.newUsername,
        comment: this.newComment,
        date: this.newDate
      };
      this.comments.push(newComment);
      this.newUsername = '';
      this.newComment = '';
      this.newDate = '';
    },
    deleteComment(index) {
      this.comments.splice(index, 1);
    }
  }
};
</script>

<template>
  <div class="comment-list">
    <h2>Daftar Komentar</h2>
    <form @submit.prevent="addComment">
      <input v-model="newUsername" type="text" placeholder="Username" required />
      <textarea v-model="newComment" placeholder="Komentar" required></textarea>
      <input v-model="newDate" type="date" required />
      <button type="submit">Tambah Komentar</button>
    </form>

    <CommentItem
      v-for="(comment, index) in comments"
      :key="index"
      :index="index"
      :username="comment.username"
      :comment="comment.comment"
      :date="comment.date"
      @delete-comment="deleteComment"
    />
  </div>
</template>

<style scoped>
.comment-list {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background-color: #fafafa;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
  color: #333;
  font-size: 24px;
  margin-bottom: 20px;
}

form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 20px;
}

input, textarea {
  padding: 10px;
  font-size: 14px;
  border-radius: 5px;
  border: 1px solid #ddd;
}

button {
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #45a049;
}
</style>
