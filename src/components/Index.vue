/* eslint-disable */
<template>
  <div class="page">
    <transition name="slide-fade">
      <ul class="bg-bubbles">
        <li v-for="i in 10" :key="i"></li>
      </ul>
    </transition>
    <div class="title">
      <h1>LIRAWX.</h1>
      <p><span>Life is short, let it be undefined;</span></p>
    </div>
    <footer>
      @ <a href="http://lirawx.me">lirawx.me</a>&nbsp;&nbsp; Since 2018
      <p>Hosted by <a href="https://pages.coding.me" style="font-weight: bold">Coding Pages</a></p>

    </footer>
  </div>
</template>

<script>
export default {
  name: 'Index',
};
</script>

<style lang="less" scoped>
@font-face {
    font-family: "STCaiyun";
    src:url("../assets/STCaiyun.woff") format("woff");
  }

.title{
    width: 100%;
    position: absolute;
    margin: 0 auto;
    top: 30%;
}

.title p {
      font-size: 2rem;
}
.title h1 {
      font-size: 4rem;
}

.wf-active .title h1{
  font-family: 'STCaiyun', Helvetica, Arial, sans-serif;
}

footer{
  width: 100%;
  position: absolute;
  margin: 0 auto;
  bottom: 10%;
  font-size: 1rem;
  color: #000;
}

footer a{
  color: #000;
  text-decoration-style: none;
}
/* 可以设置不同的进入和离开动画 */
/* 设置持续时间和动画函数 */
.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}

.bg-bubbles {
  margin: 0;
  background: linear-gradient(to bottom right, #50A3A2, #53E3A6);
  position: absolute;
  // 使气泡背景充满整个屏幕；
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  // 如果元素内容超出给定的宽度和高度，overflow 属性可以确定是否显示滚动条等行为；
  overflow: hidden;
  li {
    // 圆形
    border-radius: 50%;

    position: absolute;
    // bottom 的设置是为了营造出气泡从页面底部冒出的效果；
    bottom: -160px;
    // 默认的气泡大小；
    width: 40px;
    height: 40px;
    background-color: rgba(255, 255, 255, 0.15);
    list-style: none;
    // 使用自定义动画使气泡渐现、上升和翻滚；
    animation: square 15s infinite;
    transition-timing-function: linear;
    // 分别设置每个气泡不同的位置、大小、透明度和速度，以显得有层次感；
    &:nth-child(1) {
      left: 10%;
    }
    &:nth-child(2) {
      left: 20%;
      width: 90px;
      height: 90px;
      animation-delay: 2s;
      animation-duration: 7s;
    }
    &:nth-child(3) {
      left: 25%;
      animation-delay: 4s;
    }
    &:nth-child(4) {
      left: 40%;
      width: 60px;
      height: 60px;
      animation-duration: 8s;
      background-color: rgba(255, 255, 255, 0.3);
    }
    &:nth-child(5) {
      left: 70%;
    }
    &:nth-child(6) {
      left: 80%;
      width: 120px;
      height: 120px;
      animation-delay: 3s;
      background-color: rgba(255, 255, 255, 0.2);
    }
    &:nth-child(7) {
      left: 32%;
      width: 160px;
      height: 160px;
      animation-delay: 2s;
    }
    &:nth-child(8) {
      left: 55%;
      width: 20px;
      height: 20px;
      animation-delay: 4s;
      animation-duration: 15s;
    }
    &:nth-child(9) {
      left: 25%;
      width: 10px;
      height: 10px;
      animation-delay: 2s;
      animation-duration: 12s;
      background-color: rgba(255, 255, 255, 0.3);
    }
    &:nth-child(10) {
      left: 85%;
      width: 160px;
      height: 160px;
      animation-delay: 5s;
    }
  }
  // 自定义 square 动画；
  @keyframes square {
    0% {
      opacity: 0.2;
      transform: translateY(0px) rotate(45deg);
    }
    95% {
      opacity: 1;
      transform: translateY(-900px) rotate(135deg);
    }
    100% {
      opacity: 0;
      transform: translateY(-1000px) rotate(180deg);
    }
  }
}
</style>
