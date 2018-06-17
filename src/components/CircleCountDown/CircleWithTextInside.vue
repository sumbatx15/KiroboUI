<template>
    <div class="circle-with-text-container">
        <div class="text-in-circle" :style="{color: textColor}">
            <slot></slot>
        </div>
        <el-progress :stroke-width="4" :width="width" :show-text="false" type="circle" :color="color" :percentage="percentage"></el-progress>
    </div>
</template>

<script>
export default {
    // ["percentage", "color", "textColor", "width"]
  props: {
      width:{
          default: 200
      },
      color:{
          default : '#31cafd'
      },
      textColor:{
          default: '#1f2e71'
      },
      percentage:{
          default: 0
      }
  }
};
</script>

<style>
.circle-with-text-container {
  position: relative;
}
.text-in-circle {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
