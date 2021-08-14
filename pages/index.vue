<template>
  <div class="page wrapper">
    <div class="card">
      <div class="card__title">Valentine's Day</div>
      <div class="emoji emoji__one">🐢</div>
      <div class="emoji emoji__two">🎅</div>
      <div class="emoji emoji__three">🐶</div>
      <div class="card__container">
        <div class="content">
          <p>親愛的寶貝老婆</p>
          <p>今天是我們的第八個情人節ㄦ🧡</p>
          <p>今年的情人節卡片比較特別</p>
          <p>是用網頁做的手工卡片ㄦ🐢</p>
          <p>希望寶貝老婆會喜歡👩‍❤️‍💋‍👨</p>
          <p>希望我在老婆身邊的時候</p>
          <p>老婆的心情都是大晴天🌞</p>
          <p>我愛你ㄦ寶貝老婆😘</p>
          <p>情人節快樂💖</p>
        </div>
        <div class="heart" @click="playAudio"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    playAudio() {
      const audio = document.createElement("audio");
      audio.src = require('@/assets/music.mp3');
      audio.play();
    },
  },
}
</script>

<style lang="scss">
.wrapper {
  position: absolute;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgb(168, 134, 134);
}
.card {
  width: 50rem;
  height: 30rem;
  border: solid 0.15rem #f7afbb;
  box-shadow: 0 0 0.5rem #f199a8;
  border-radius: 0.3rem;
  background-color: #ffc0cb;
  position: relative;
  overflow: hidden;
  animation: fadein ease-in 1s;
  animation-fill-mode: forwards;
  opacity: 0;

  &::before {
    transform: rotate(45deg);
    content: '-';
    color: transparent;
    background-color: #ff0;
    width: 1.5rem;
    height: 10rem;
    position: absolute;
    border-left: solid 0.15rem red;
    border-right: solid 0.15rem red;
    border-radius: 0.1rem;
    top: -3rem;
    left: 1rem;
  }

  &__title {
    position: relative;
    font-family: 'Style Script', cursive;
    font-size: 5rem;
    text-align: center;
    margin-top: 1rem;
    opacity: 0;
    animation: fadein ease-in 1s;
    animation-delay: 1s;
    animation-fill-mode: forwards;
  }

  &__container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}

.emoji {
  position: absolute;
  width: 2rem;
  font-size: 2rem;
  transform-origin: center;
  transform: rotate(0deg);
  animation: swing infinite ease-in 2s;

  &__one {
    top: 11%;
    left: 8%;
  }

  &__two {
    top: 8%;
    left: 90%;
  }

  &__three {
    bottom: 8%;
    right: 13%;
  }
}

.content {
  font-size: 1.5rem;
  line-height: 2.5rem;
  letter-spacing: 0.3rem;

  p {
    animation: fadein ease-in 2s;
    animation-fill-mode: forwards;
    opacity: 0;
    &:nth-child(1) {
      animation-delay: 2s;
    }
    &:nth-child(2) {
      animation-delay: 4s;
    }
    &:nth-child(3) {
      animation-delay: 6s;
    }
    &:nth-child(4) {
      animation-delay: 8s;
    }
    &:nth-child(5) {
      animation-delay: 10s;
    }
    &:nth-child(6) {
      animation-delay: 12s;
    }
    &:nth-child(7) {
      animation-delay: 14s;
    }
    &:nth-child(8) {
      animation-delay: 16s;
    }
    &:nth-child(9) {
      animation-delay: 18s;
      font-size: 2rem;
    }
  }
}

.heart {
  transform: scale(1);
  width: 10rem;
  height: 10rem;
  opacity: 0;
  animation-fill-mode: forwards;
  animation-name: fadein, heart-beat;
  animation-delay: 2s, 2s;
  animation-iteration-count: 1, infinite;
  animation-duration: 2s, 2s;
  animation-timing-function: ease-in, ease;

  &::before,
  &::after {
    content: '';
    position: absolute;
    border-radius: 3.2rem 3.2rem 0 0;
    width: 4.3rem;
    height: 6.8rem;
    background: red;
    cursor: pointer;
    top: 40%;
  }

  &::before {
    left: 43%;
    transform: rotate(-45deg) translateY(-50%);
  }

  &::after {
    left: 13%;
    transform: rotate(45deg) translateY(-50%);
  }
}

@keyframes fadein {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

@keyframes heart-beat {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.1);
  }

  100% {
    transform: scale(1);
  }
}

@keyframes swing {
  0% {
    transform: rotate(0deg);
  }

  25% {
    transform: rotate(-45deg);
  }

  50% {
    transform: rotate(0deg);
  }

  75% {
    transform: rotate(45deg);
  }

  100% {
    transform: rotate(0deg);
  }
}
</style>
