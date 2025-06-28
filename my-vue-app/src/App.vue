<template>
  <div>
    <h1>{{ message }}</h1>
    <input v-model="message" />
    <HelloWorld msg="やっほー！" />
    <button @click="sayHello">クリック</button>
    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>
    <p v-if="message.length > 5">文字が多いよ！</p>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  components: {
    HelloWorld, // ✅ ここで登録！
  },
  data() {
    return {
      message: "こんにちは Vue!",
      items: ["りんご", "みかん", "ぶどう"],
    };
  },
  methods: {
    sayHello() {
      alert(`こんにちは！メッセージは: ${this.message}`);
    },
  },
};
</script>

<style scoped>
h1 {
  color: #42b983;
}
</style>
