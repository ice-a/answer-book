<template>
  <div id="app">
    <h1>答案之书</h1>
    <input v-model="question" placeholder="输入你的问题" />
    <button @click="getAnswer">获取答案</button>
    <div v-if="answer">{{ answer }}</div>
  </div>
</template>

<script>
import answers from '/src/assets/answers.json';

export default {
  data() {
    return {
      question: '',
      answer: '',
      answers: answers,
    };
  },
  methods: {
    getAnswer() {
      // 从答案数组中随机选择一个答案
      const randomIndex = Math.floor(Math.random() * this.answers.length);
      this.answer = this.answers[randomIndex];
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}
input {
  margin-bottom: 20px;
  padding: 10px;
  width: 300px;
}
button {
  padding: 10px 20px;
  cursor: pointer;
}
</style>