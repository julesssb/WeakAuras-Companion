<template>
  <div class="checkbox" @click="triggerInputClick">
    <input
      type="checkbox"
      ref="checkbox"
      v-bind="$attrs"
      :checked="value"
      @change="$emit('input', $event.target.checked)"
    />
    <div class="checkbox__box" :class="{ 'checkbox__box--checked': value }" />
    <label> <slot></slot> </label>
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
  methods: {
    triggerInputClick() {
      this.$refs.checkbox.click();
    }
  },
  props: ["value"]
};
</script>

<style scoped lang="scss">
input[type="checkbox"] {
  display: none;
}
input[type="checkbox"]:disabled + .checkbox__box {
  background-color: #dddddd;
  box-shadow: none;
  cursor: auto;
}
input[type="checkbox"] + .checkbox__box:focus {
  box-shadow: 0 0 0 3px rgba(0, 0, 0, 0.12);
}
.checkbox {
  align-items: center;
  cursor: pointer;
  display: flex;
  flex-direction: row;
  user-select: none;
}
.checkbox__box {
  background-color: #e6e6e6;
  border-radius: 2px;
  height: 20px;
  margin-right: 10px;
  width: 20px;
}
.checkbox__box--checked {
  background-color: #191919;
  background-image: url("~@/assets/checkmark.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: 15px;
}
</style>
