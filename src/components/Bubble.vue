<template>
  <div
    class="bubble"
  />
</template>

<script>
export default {
  name: 'Bubble',
  data() {
    return {
      isHovering: false
    }
  }
}
</script>

<style lang="scss">
@keyframes spin {
  0% {
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}

.bubble {
  position: absolute;
  left: 10%;
  top: 30%;
  height: 200px;
  width: 200px;
  border-radius: 50%;
  background-color: #000;
  -webkit-box-shadow: 0px 20px 55px -9px rgba(0,0,0,0.75);
  -moz-box-shadow: 0px 20px 55px -9px rgba(0,0,0,0.75);
  box-shadow: 0px 20px 55px -9px rgba(0,0,0,0.75);
}
</style>
