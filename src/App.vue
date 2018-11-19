<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <p class="desc">This is my css <span class="playground" v-for="letter in letters">{{letter}}</span>.</p>
    <p class="desc">Pick a <span class="desc-dot">dot.</span></p>
    <Bubble />
  </div>
</template>

<script>
import Bubble from './components/Bubble.vue'
export default {
  name: 'app',
  components: {
    Bubble
  },
  data () {
    return {
      title: 'Hello. I\'m Marie.',
      letters: ['p', 'l', 'a', 'y', 'g', 'r', 'o', 'u', 'n', 'd']
    }
  }
}
</script>

<style lang="scss">

@keyframes jump {
  0% {
    transform: translateY(0) scale(1);
  }
  10% {
    transform: translateY(-5px) scale(1.1);
  }
  18% {
    transform: translateY(0) scale(1);
  }
  100% {
    transform: translateY(0) scale(1);
  }
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
  padding: 50px;
  position: relative;
  height: 100%;
}

h1 {
  font-weight: normal;
  position: relative;

  &::after {
    width: 250px;
    position: absolute;
    left: 0;
    content: '';
    height: 20px;
    background: #000;
    opacity: .3;
    transform: translate(15px, 22px) skewX(10deg);
  }
}

.desc {
  font-size: 1.2rem;
  letter-spacing: 1.2px;

  .playground {
    display: inline-block;

    @for $i from 1 through 10 {
      &:nth-child(#{$i})  {

        animation: jump 3s ease-in;
        animation-iteration-count: infinite;
        animation-delay:  #{$i * .1}s;
        animation-timing-function: ease;
      }

    }
  }
  .desc-dot {
    color: #d299c2;
    position: relative;

    &::after {
      content: '';
      position: absolute;
      background: #000;
      display: inline-block;
      border-radius: 50%;
      width: 48px;
      height: 48px;
      left: -5px;
      top: -10px;
      z-index: -1;
      -webkit-box-shadow: 0px 20px 55px -9px rgba(0,0,0,0.75);
      -moz-box-shadow: 0px 20px 55px -9px rgba(0,0,0,0.75);
      box-shadow: 0px 20px 55px -9px rgba(0,0,0,0.75);
    }
  }
}

</style>
