<template>
<label class="switch">
  <input type="checkbox" :checked="value" @click.prevent="clickHandler" v-bind="{ disabled, readonly, required }">
  <span :style="checkedBg"></span>
</label>
</template>

<script>
const colorRegExp = /(#(?:[0-9a-f]{2}){2,4}|(#[0-9a-f]{3})|(rgb|hsl)a?\((-?\d+%?[,\s]+){2,3}\s*[\d.]+%?\))/i

export default {
  name: 'vue-simple-switch',
  props: {
    value: {
      type: Boolean,
      default: false
    },
    color: {
      type: String,
      default: '#5d9cec',
      validator: color => colorRegExp.test(color)
    },
    disabled: {
      type: Boolean,
      default: false
    },
    readonly: {
      type: Boolean,
      default: false
    },
    required: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    clickHandler () {
      this.$emit('input', !this.value)
    }
  },
  computed: {
    checkedBg () {
      return this.value ? `background-color: ${this.color}; border-color: ${this.color};` : ''
    }
  }
}
</script>

<style scoped>
.switch {
  cursor: pointer;
}
.switch input {
  display: none;
}
.switch span {
  position: relative;
  display: inline-block;
  width: 40px;
  height: 20px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 100px;
  transition: left .5s, background-color .5s, border-color .5s;
  box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.1) inset;
  vertical-align: middle;
}
.switch span::after {
  content: '';
  position: absolute;
  background-color: #fff;
  top: 0;
  left: 0;
  height: 18px;
  width: 18px;
  border: 1px solid #ddd;
  border-radius: 400px;
  box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
}
.switch input:checked + span {
  background-color: #5d9cec;
  border-color: #5d9cec;
  transition: left .5s, background-color .5s, border-color .5s;
}
.switch input:checked + span::after {
  left: 50%;
  transition: left .2s, background-color .2s, border-color .2s;
}
.switch input:disabled + span {
  background-color: #f1f1f1;
  cursor: not-allowed;
}
</style>
