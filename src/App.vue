<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <button class="button-primary" @click="sendGTMHandler()">Send GTM Event</button>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() {
    return {
      userID: 'ABC-123456'
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    sendGTMHandler() {
      const vm = this;
      vm.$gtm.trackEvent({
        event: 'click-event',
        category: '點擊事件', // 類別 字元(必填)
        action: 'click', // 動作 字元(必填)
        label: vm.userID, // 標籤 字元(選填)
        value: null, // 標籤 數字(選填)
      });
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.button-primary {
  display: block;
  background: blue;
  color: #FFFFFF;
  padding: 10px;
  border: 2px solid #000;
  margin: 0 auto;
}
</style>
