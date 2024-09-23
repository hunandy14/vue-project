<template>
  <button
    :style="buttonStyle"
    @mouseover="hover = true"
    @mouseleave="hover = false"
    @mousedown="active = true"
    @mouseup="active = false"
  >
    <slot>ModernButton</slot>
  </button>
</template>

<script>
export default {
  name: 'ModernButton',
  props: {
    backgroundColor: { type: String, default: '#ffffff' },
    hoverColor: { type: String, default: '#eeeeee' },
    activeColor: { type: String, default: '#cccccc' },
    afterActiveColor: { type: String, default: '#cccccc' },
    borderColor: { type: String, default: null }, // 預設值依賴於 activeColor
    borderWidth: { type: String, default: '1px' }
  },
  data() {
    return {
      hover: false,
      active: false
    };
  },
  computed: {
    effectiveBorderColor() {
      // 如果 borderColor 被明確設置，則使用它；否則使用 activeColor
      return this.borderColor || this.activeColor;
    },
    buttonStyle() {
      let bgColor = this.backgroundColor;
      if (this.active) {
        bgColor = this.activeColor;
      } else if (this.hover) {
        bgColor = this.hoverColor;
      }

      return {
        backgroundColor: bgColor,
        borderColor: this.effectiveBorderColor,
        borderWidth: this.borderWidth,
        borderStyle: 'solid',
        outline: 'none',
        transition: 'background-color 0.3s, border-color 0.3s'
      };
    }
  }
}
</script>


<style scoped>
button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
</style>
