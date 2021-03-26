<template>
  <div class="box">
    <span class="text">{{ text }}</span>
  </div>
</template>

<script>
export default {
  name: 'Box',
  props: [ 'id', 'text' ],
  data() {
    return {
      isDelete: false
    }
  }
}
</script>

<style scoped>
.box {
  background: #F7F7F7;
  width: 10rem;
  height: 10rem;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10%;
  box-shadow: 10px 10px 20px 1px rgba(0, 0, 0, .05);
  animation: boxHoverExit 250ms;
}

.text {
  margin: .5rem;
  overflow: hidden;
  text-overflow: ellipsis;
}

.box:hover {
  box-shadow: 10px 10px 20px 1px rgba(0, 0, 0, .15);
  animation: boxHover 250ms;
  animation-fill-mode: forwards;
}

@keyframes boxHover {
  from { transform: translate(0, 0) }
  to { transform: translate(-5px, -5px) }
}

@keyframes boxHoverExit {
  from { transform: translate(-5px, -5px) }
  to { transform: translate(0, 0) }
}
</style>
