<script>
export default {
  props: {
    username: {
      type: String,
      required: true
    },
    comment: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    },
    index: {
      type: Number,
      required: true
    }
  },
  methods: {
    deleteComment() {
      this.$emit('delete-comment', this.index);
    }
  }
};
</script>

<template>
  <div class="comment-item">
    <div class="comment-header">
      <span class="username">{{ username }}</span>
      <span class="date">{{ date }}</span>
      <button class="delete-btn" @click="deleteComment">Hapus</button>
    </div>
    <p class="comment">{{ comment }}</p>
  </div>
</template>

<style scoped>
.comment-item {
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 15px;
  margin: 10px 0;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.comment-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.comment-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.username {
  font-weight: bold;
  color: #4a90e2;
  font-size: 16px;
}

.date {
  font-size: 12px;
  color: #888;
}

.comment {
  font-size: 14px;
  color: #333;
  line-height: 1.5;
}

.delete-btn {
  background-color: #e74c3c;
  color: white;
  border: none;
  padding: 5px 10px;
  font-size: 12px;
  cursor: pointer;
  border-radius: 4px;
  transition: background-color 0.3s;
}

.delete-btn:hover {
  background-color: #c0392b;
}
</style>
