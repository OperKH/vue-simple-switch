<template>
<section id="app">
  <h2>Vue simple Switch Usage Exsample:</h2>
  <div class="line">
    <h3>2-way data binding:</h3>
    <vue-simple-switch v-model="isSwitchedOn1" />
    <input type="checkbox" v-model="isSwitchedOn1">
  </div>

  <div class="line">
    <h3>1-way data binding:</h3>
    <vue-simple-switch :value="isSwitchedOn2" />
    <input type="checkbox" v-model="isSwitchedOn2">
  </div>

  <div class="line">
    <h3>Readonly:</h3>
    <vue-simple-switch :value="isSwitchedOn3" readonly />
    <input type="checkbox" v-model="isSwitchedOn3">
  </div>

  <div class="line">
    <h3>Disabled:</h3>
    <vue-simple-switch v-model="isSwitchedOn4" disabled />
    <input type="checkbox" v-model="isSwitchedOn4">
  </div>

  <div class="line">
    <h3>Set color and make it required:</h3>
    <vue-simple-switch v-model="isSwitchedOn5" color="#ff902b" required />
    <input type="checkbox" v-model="isSwitchedOn5">
  </div>
</section>
</template>

<script>
import VueSimpleSwitch from './components/vueSimpleSwitch'

export default {
  name: 'app',
  components: {
    VueSimpleSwitch
  },
  data () {
    return {
      isSwitchedOn1: false,
      isSwitchedOn2: false,
      isSwitchedOn3: true,
      isSwitchedOn4: false,
      isSwitchedOn5: false
    }
  }
}
</script>

<style scoped>
#app {
  max-width: 900px;
  margin: 0 auto;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.line {
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
.line h3 {
  flex-basis: 100%;
}
</style>
