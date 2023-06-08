<template>
  <div id="app">
    <h1 class="gradient-text">Dazzling开发的记牌器</h1>
    <p class="gradient-text">这是我开发的记牌器，专门给 表示记牌很困难的小趴菜 使用哦！！！</p>
    <p>项目地址：<a href="https://github.com/misDazzling/JiPaiQI" target="_blank">https://github.com/misDazzling/JiPaiQI</a></p>
     <p class="gradient-text">如有帮助，帮忙点一个star哦！！！</p>
    <label for="decks">选择几副牌:</label>
    <input type="number" id="decks" v-model="decks" min="1" @change="initializeCards" />
    
    <div class="cards-container">
      <div
        v-for="(card, index) in cards"
        :key="index"
        class="card"
        @click="selectCard(index)"
      >
        {{ card.name }}
        <span class="remaining">({{ card.remaining }})</span>
      </div>
    </div>
    <button @click="undoSelect">撤销上一次操作</button>
  </div>

</template>

<script>
export default {
  name:'CardRecorder',
  data() {
    return {
      decks: 1,
      cards: [],
      history: [], // 添加 history 属性
    };
  },
  methods: {
    initializeCards() {
      const cardTypes = [
        "3",
        "4",
        "5",
        "6",
        "7",
        "8",
        "9",
        "10",
        "J",
        "Q",
        "K",
        "A",
        "2",
        "小王",
        "大王",
      ];
      this.cards = cardTypes.map((card) => ({
        name: card,
        total: card === "小王" || card === "大王" ? this.decks * 1 : this.decks * 4,
        remaining: card === "小王" || card === "大王" ? this.decks * 1 : this.decks * 4,
      }));
    },
    selectCard(index) {
    if (this.cards[index].remaining > 0) {
      // 将操作对象加入历史数组
      this.history.push({ index, remaining: this.cards[index].remaining });
      this.cards[index].remaining--;
      console.log('selectCard方法被调用了');
    }
  },
  undoSelect() {
    // 从历史数组末尾开始逐个还原
    const lastOperation = this.history.pop();
    if (lastOperation) {
      this.cards[lastOperation.index].remaining = lastOperation.remaining;
    }
  },
  },
  mounted() {
    this.initializeCards();
  },
};
</script>

<style scoped>
#app {
  text-align: center;
}
p {
  word-wrap: break-word;
}
a {
  word-wrap: break-word;
}
.gradient-text {
  background: -webkit-linear-gradient(#ee7752, #e73c7e, #23a6d5, #23d5ab);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-text-animation 10s ease-in-out infinite;
}

/* 使用动画效果让渐变色持续运动 */
@keyframes gradient-text-animation {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
}
.cards-container {
 
  display: flex;
  flex-wrap: wrap;
  justify-content: center!important;
  margin-top: 20px;

}

.card {
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 15px;
  margin: 5px;
  cursor: pointer;
  min-width: 50px;
  min-height: 10px;
  height: 40px;
  width: 60px;
}

.remaining {
  font-size: 0.8em;
  color: #888;
}
button {
  background-color: #23a6d5;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 1em;
  margin-top: 20px;
}
</style>
