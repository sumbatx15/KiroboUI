<template>
    <el-popover placement="right" width="300" trigger="hover">
        <slot></slot>
        <div class="hot-spot-container" :style="stylePosition" slot="reference">
            <div class="hot-spot-btn">
                <div class="hot-spot-dot"></div>
            </div>
        </div>
    </el-popover>
</template>

<script>
export default {
    props:['top','left'],
    computed:{
        stylePosition(){
            return{
                top: this.top,
                left: this.left
            }
        }
    }
};
</script>

<style>
.hot-spot-container {
  cursor: pointer;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
}
.hot-spot-dot {
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.205);
  width: 10px;
  height: 10px;
  border-radius: 100%;
  background: white;
}
.hot-spot-btn {
  background: #31cafd;
  width: 25px;
  height: 25px;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: flicker 1.3s infinite;
}
@keyframes flicker {
  0% {
      transform: scale(1)
  }
  50% {
      transform: scale(1.2)

  }
  100% {
      transform: scale(1)

  }
}
</style>
