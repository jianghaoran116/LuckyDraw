<template>
  <TheGame
      :prizesList="prizes"
      :resultIndex="resultIndex"
      :test="test"
      @canShowResultPop="canShowResultPopHandle"
  />
  <div class="btn" @click="onStart">抽奖</div>
</template>

<script>
import TheGame from './components/TheGame.vue'
import { prizes } from './config.js'

export default {
  name: 'App',
  components: {
    TheGame
  },
  data() {
    return {
      prizes: prizes,
      resultIndex: -1,
      test: 1,
    }
  },
  methods: {
    onStart() {
      this.resultIndex = 3;
      console.log(this.resultIndex);
    },
    canShowResultPopHandle() {
      alert('抽奖成功');
      // 适当时机清楚抽奖记录
      setTimeout(() => {
        this.resultIndex = -1;
      }, 3000)
    }
  }
}
</script>
<style>
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 100px;
  height: 40px;
  border-radius: 50px;
  background: #fc696a;
  color: #fff;
}
</style>
